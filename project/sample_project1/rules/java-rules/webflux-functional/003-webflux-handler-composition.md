---
description: "Best practices for composing WebFlux Router and Handler functions."
globs: ["**/*RouterConfig.java", "**/*Handler.java"]
alwaysApply: false
---
WebFlux Functional Endpoints (Router/Handler) Composition:
- Router functions (RouterFunction<ServerResponse>) should be defined as @Beans in @Configuration classes.
- Handler functions should be stateless and reside in dedicated @Component classes.
- Use RouterFunctions.route() and compose with andRoute().
- Apply predicates for HTTP methods, paths, headers, and query parameters.
- Ensure ServerResponse.ok(), notFound(), badRequest(), etc., are used appropriately.
