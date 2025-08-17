---
description: "Guidelines for Spring dependency injection."
alwaysApply: true
---
Spring Dependency Injection:
- Prefer constructor injection for mandatory dependencies.
- Use @Autowired for fields only in specific cases like test classes or when using @Value.
- Keep dependencies as specific as possible (interface over implementation if an interface exists).
