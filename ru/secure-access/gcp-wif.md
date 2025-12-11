# Безопасный доступ к GCP с помощью Workload Identity Federation

Этот метод является **рекомендуемым** для настройки CI/CD (например, GitHub Actions) и позволяет получить временные учетные данные GCP без необходимости хранить долгоживущие ключи сервисного аккаунта.

## Принцип работы

1.  **GitHub** генерирует уникальный OIDC токен для каждого запуска вашего workflow.
2.  **GCP IAM** доверяет GitHub как провайдеру идентификации через Workload Identity Federation.
3.  GitHub Action передает свой OIDC токен в GCP.
4.  **GCP STS** проверяет токен и, если он валиден, выдает вашему workflow временные учетные данные для имперсонации указанного сервисного аккаунта.

## Пошаговая настройка

### Шаг 1: Включите необходимые API

```bash
gcloud services enable iamcredentials.googleapis.com
gcloud services enable sts.googleapis.com
```

### Шаг 2: Создайте пул Workload Identity

```bash
gcloud iam workload-identity-pools create "github-pool" \
  --project="YOUR_PROJECT_ID" \
  --location="global" \
  --display-name="GitHub Actions Pool"
```

### Шаг 3: Создайте провайдера Workload Identity

```bash
gcloud iam workload-identity-pools providers create-oidc "github-provider" \
  --project="YOUR_PROJECT_ID" \
  --location="global" \
  --workload-identity-pool="github-pool" \
  --display-name="GitHub Provider" \
  --attribute-mapping="google.subject=assertion.sub,attribute.actor=assertion.actor,attribute.repository=assertion.repository" \
  --issuer-uri="https://token.actions.githubusercontent.com"
```

### Шаг 4: Создайте сервисный аккаунт

```bash
gcloud iam service-accounts create github-actions-sa \
  --project="YOUR_PROJECT_ID" \
  --display-name="GitHub Actions Service Account"
```

Предоставьте необходимые права сервисному аккаунту:

```bash
gcloud projects add-iam-policy-binding YOUR_PROJECT_ID \
  --member="serviceAccount:github-actions-sa@YOUR_PROJECT_ID.iam.gserviceaccount.com" \
  --role="roles/editor"
```

### Шаг 5: Разрешите пулу Workload Identity имперсонировать сервисный аккаунт

```bash
gcloud iam service-accounts add-iam-policy-binding \
  github-actions-sa@YOUR_PROJECT_ID.iam.gserviceaccount.com \
  --project="YOUR_PROJECT_ID" \
  --role="roles/iam.workloadIdentityUser" \
  --member="principalSet://iam.googleapis.com/projects/PROJECT_NUMBER/locations/global/workloadIdentityPools/github-pool/attribute.repository/v-grand/YOUR_REPO"
```

**Важно**: Замените `PROJECT_NUMBER` на номер вашего проекта GCP (не ID) и `v-grand/YOUR_REPO` на ваш репозиторий.

### Шаг 6: Получите имя ресурса провайдера Workload Identity

```bash
gcloud iam workload-identity-pools providers describe "github-provider" \
  --project="YOUR_PROJECT_ID" \
  --location="global" \
  --workload-identity-pool="github-pool" \
  --format="value(name)"
```

Сохраните это значение - оно понадобится в вашем GitHub Actions workflow.

### Шаг 7: Обновите GitHub Actions Workflow

```yaml
name: Deploy to GCP via WIF

on:
  push:
    branches: [main]

jobs:
  deploy:
    name: Deploy to GCP
    runs-on: ubuntu-latest
    permissions:
      id-token: write # Необходимо для получения OIDC токена
      contents: read

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Authenticate to Google Cloud
      uses: google-github-actions/auth@v1
      with:
        workload_identity_provider: 'projects/PROJECT_NUMBER/locations/global/workloadIdentityPools/github-pool/providers/github-provider'
        service_account: 'github-actions-sa@YOUR_PROJECT_ID.iam.gserviceaccount.com'

    - name: Set up Cloud SDK
      uses: google-github-actions/setup-gcloud@v1

    - name: Use gcloud CLI
      run: gcloud info
```

Теперь вам больше не нужны файлы ключей сервисного аккаунта в вашем репозитории!
