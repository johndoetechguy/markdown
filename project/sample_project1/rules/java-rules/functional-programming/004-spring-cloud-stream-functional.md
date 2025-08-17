---
description: "Guidelines for defining functional message processing in Spring Cloud Stream."
globs: ["**/*Application.java", "**/*Config.java"]
alwaysApply: false
---
Spring Cloud Stream Functional Programming Model:
- Define producers as Supplier<Flux<Message<?>>> beans.
- Define processors as Function<Flux<Message<I>>, Flux<Message<O>>> beans.
- Define consumers as Consumer<Flux<Message<?>>> beans.
- Use org.springframework.messaging.Message for headers and payloads.
- Avoid side effects in Function beans; Consumer beans are suitable for side effects.
- Use spring.cloud.function.definition in application.yml to specify active functions.
