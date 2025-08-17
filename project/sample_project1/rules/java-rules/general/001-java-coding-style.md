---
description: "Enforce consistent Java coding style and conventions for the project."
alwaysApply: true
---
Java Coding Standards:
- Use Google Java Format for code formatting.
- Follow standard Spring Boot project structure (controllers, services, repositories, models, configs).
- Use Lombok annotations (@Data, @NoArgsConstructor, @AllArgsConstructor, @Builder, @Value) for boilerplate reduction where appropriate.
- Prefer final for method parameters and local variables where possible.
- Use meaningful and descriptive names for classes, methods, and variables (e.g., productId not id).
- Comments should explain why something is done, not what is done (unless the what is complex).
- Avoid magic numbers and strings; use constants or enums.
