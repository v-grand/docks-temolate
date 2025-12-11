# Platform Overview

This page provides a general overview of the platform's architecture, describing its key components and their purpose.

## template-platform

**The build and launch point for the entire platform.**

`template-platform` is the central component that unites all other services, ensuring their interaction and deployment. It serves as the foundation for the entire ecosystem, providing common configurations, build tools, and launch mechanisms.

## Platform Services

Below is a list of the main services that make up the platform:

### [template-user-service](template-user-service.md)

**Authentication, roles, sessions.**
A user management service responsible for registration, authentication, user role management, and sessions.

### [template-wallet-service](template-wallet-service.md)

**Wallets, signatures, Web3 integration.**
A service for managing digital wallets, processing cryptographic signatures, and integrating with Web3 technologies.

### [template-payment-service](template-payment-service.md)

**Payments, gateways, Web3/Fiat.**
A payment processing service supporting various payment gateways, as well as operations with Web3 assets and traditional (Fiat) currencies.

### [template-order-service](template-order-service.md)

**Orders, statuses, cart.**
A service for managing orders, tracking their statuses, and working with the shopping cart.

### [template-product-service](template-product-service.md)

**Catalog, products, categories.**
A service for managing the product catalog, their descriptions, categories, and attributes.

### [template-discount-service](template-discount-service.md)

**Discounts, promotions, coupons.**
A service for managing discounts, promotions, and coupons applied to products and orders.
