# Witamy w Dokumentacji Platformy v-grand

Witamy w kompleksowej dokumentacji ekosystemu **v-grand**. Tutaj znajdziesz informacje o różnych komponentach platformy, ich przeznaczeniu i sposobach użycia.

## 📚 Przegląd Platformy

Aby uzyskać ogólne zrozumienie struktury i podstawowych usług platformy, odwiedź stronę:

[**Przegląd Platformy**](platform-overview.md)

## 🚀 Szybki start

### Dla nowych projektów

1.  **Sklonuj szablon:**
    ```bash
    git clone https://github.com/v-grand/infra-template.git my-new-project
    cd my-new-project
    ```

2.  **Skonfiguruj środowisko:**
    ```bash
    cp terraform.tfvars.example terraform.tfvars
    # Edytuj terraform.tfvars z własnymi ustawieniami
    ```

3.  **Wdróż:**
    ```bash
    terraform init
    terraform plan
    terraform apply
    ```

### Dla istniejących projektów

Wybierz odpowiednie repozytorium:

-   **Wdrożenie AWS** → [infra-aws](aws.md)
-   **Wdrożenie GCP** → [gcp/index.md](gcp/index.md)
-   **Kubernetes** → [infra-k8s.md](infra-k8s.md)
-   **Monitorowanie** → [infra-monitoring.md](infra-monitoring.md)

## 🔗 Zasoby zewnętrzne

-   [Dokumentacja Terraform](https://www.terraform.io/docs)
-   [Dokumentacja GitHub Actions](https://docs.github.com/en/actions)
-   [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
-   [Google Cloud Architecture Center](https://cloud.google.com/architecture)

## 🤝 Wkład w projekt

Zapraszamy do współtworzenia projektu! Prosimy zapoznać się z wytycznymi dotyczącymi wkładu w poszczególnych repozytoriach.

## 📄 Licencja

Wszystkie repozytoria są objęte licencją MIT, chyba że zaznaczono inaczej.
