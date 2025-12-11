# Przegląd Platformy

Ta strona zawiera ogólny przegląd architektury platformy, opisując jej kluczowe komponenty i ich przeznaczenie.

## template-platform

**Punkt kompilacji i uruchamiania całej platformy.**

`template-platform` jest centralnym komponentem, który łączy wszystkie inne usługi, zapewniając ich interakcję i wdrożenie. Służy jako podstawa dla całego ekosystemu, dostarczając wspólne konfiguracje, narzędzia do budowania i mechanizmy uruchamiania.

## Usługi Platformy

Poniżej znajduje się lista głównych usług, które tworzą platformę:

### [template-user-service](template-user-service.md)

**Uwierzytelnianie, role, sesje.**
Usługa zarządzania użytkownikami, odpowiedzialna za rejestrację, uwierzytelnianie, zarządzanie rolami użytkowników i sesjami.

### [template-wallet-service](template-wallet-service.md)

**Portfele, podpisy, integracja Web3.**
Usługa do zarządzania cyfrowymi portfelami, przetwarzania podpisów kryptograficznych i integracji z technologiami Web3.

### [template-payment-service](template-payment-service.md)

**Płatności, bramki, Web3/Fiat.**
Usługa przetwarzania płatności, obsługująca różne bramki płatności, a także operacje z aktywami Web3 i tradycyjnymi (Fiat) walutami.

### [template-order-service](template-order-service.md)

**Zamówienia, statusy, koszyk.**
Usługa do zarządzania zamówieniami, śledzenia ich statusów i pracy z koszykiem zakupów.

### [template-product-service](template-product-service.md)

**Katalog, produkty, kategorie.**
Usługa do zarządzania katalogiem produktów, ich opisami, kategoriami i atrybutami.

### [template-discount-service](template-discount-service.md)

**Rabaty, promocje, kupony.**
Usługa do zarządzania rabatami, promocjami i kuponami stosowanymi do produktów i zamówień.
