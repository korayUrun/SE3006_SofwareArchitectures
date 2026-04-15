# LAB REPORT

## Discussion: Layered Architecture vs Modular Architecture

In this lab, we can clearly see the difference between two architectural approaches.

In a layered architecture, code is organized by technical layers (controller, service, repository). This is easy to start with, but over time one layer may access internal details of another part of the system. This increases coupling.

In a modular architecture, the system is organized by business domains instead of technical layers. In this project, the system is split into catalog and orders modules. Each module hides its internal details and exposes only the required public API.

Benefits of this approach:
- Information hiding is applied more effectively.
- Coupling between modules is reduced.
- Changes are more controlled and isolated.
- Maintenance and testing become easier.

In summary, layered architecture organizes code by technical responsibilities, while modular architecture defines boundaries by business capabilities. This leads to a more loosely coupled and maintainable system.

### Trade-offs

Layered architecture trade-offs:
- Pros: Simple to understand at the beginning, fast to develop for small projects, and familiar for many teams.
- Cons: Domain logic can be scattered across layers, cross-module access can increase coupling, and boundaries are harder to enforce as the system grows.

Modular architecture trade-offs:
- Pros: Stronger module boundaries, better information hiding, and easier long-term maintenance and evolution.
- Cons: Requires more initial design effort, dependency wiring can be more explicit/verbose, and teams must follow module boundaries consistently.

For this lab size, layered architecture is quicker to start, but modular architecture is a better choice for scalability and maintainability.

## Tasks Completed (README Task 1-5)

- Task 1 (Catalog internal logic): Implemented ProductRepository findById and save methods, added constructor injection in CatalogServiceImpl, and implemented stock check/reduce flow.
- Task 2 (Catalog factory): Implemented CatalogFactory.create() to wire ProductRepository and CatalogServiceImpl and return CatalogService.
- Task 3 (Orders logic): Implemented constructor injection in OrderService, completed placeOrder flow via CatalogService API, and added try-catch handling in OrderController.
- Task 4 (Orders factory): Implemented OrdersFactory.create() to wire OrderRepository, OrderService, and OrderController.
- Task 5 (Main bootstrapping): Created modules through factories and executed test scenarios through OrderController.
