# template-user-service

Ten podmoduł to szablon usługi do zarządzania użytkownikami. Zapewnia podstawową strukturę i funkcjonalność do tworzenia mikroserwisów skoncentrowanych na obsłudze danych użytkowników.

## 🚀 Funkcje

- **Zarządzanie użytkownikami**: Rejestracja, uwierzytelnianie, profile użytkowników.
- **Elastyczna architektura**: Łatwo rozszerzalna i konfigurowalna dla różnych potrzeb.
- **Integracja**: Możliwość integracji z innymi usługami i systemami.

## 🛠️ Wymagania wstępne

- [Java Development Kit (JDK)](https://www.oracle.com/java/technologies/downloads/) (wersja 17 lub wyższa)
- [Maven](https://maven.apache.org/download.cgi)
- [Docker](https://www.docker.com/get-started) (do lokalnego wdrożenia)

## 📖 Użycie

Aby uruchomić usługę lokalnie:

```bash
# Sklonuj repozytorium
git clone https://github.com/v-grand/template-user-service.git
cd template-user-service

# Zbuduj projekt
mvn clean install

# Uruchom aplikację
java -jar target/user-service-0.0.1-SNAPSHOT.jar
```

Więcej szczegółowych informacji można znaleźć w [głównej dokumentacji infra-docks](infra-docks/docs/pl/index.md).
