# template-rest-api

Ten podmoduł to szablon do tworzenia interfejsów API RESTful. Zapewnia podstawową strukturę do szybkiego wdrażania nowych usług API, zgodnie z nowoczesnymi praktykami rozwoju.

## 🚀 Funkcje

- **Szybkie wdrożenie**: Gotowa struktura do tworzenia nowych interfejsów API.
- **Standaryzacja**: Zgodność z zasadami RESTful.
- **Rozszerzalność**: Łatwo adaptowalny do różnych wymagań biznesowych.

## 🛠️ Wymagania wstępne

- [Java Development Kit (JDK)](https://www.oracle.com/java/technologies/downloads/) (wersja 17 lub wyższa)
- [Maven](https://maven.apache.org/download.cgi)
- [Docker](https://www.docker.com/get-started) (do lokalnego wdrożenia)

## 📖 Użycie

Aby uruchomić usługę lokalnie:

```bash
# Sklonuj repozytorium
git clone https://github.com/v-grand/template-rest-api.git
cd template-rest-api

# Zbuduj projekt
mvn clean install

# Uruchom aplikację
java -jar target/rest-api-0.0.1-SNAPSHOT.jar
```

Więcej szczegółowych informacji można znaleźć w [głównej dokumentacji infra-docks](infra-docks/docs/pl/index.md).
