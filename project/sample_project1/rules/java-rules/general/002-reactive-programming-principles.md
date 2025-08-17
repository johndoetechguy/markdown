---
description: "Guide AI on Spring WebFlux and Reactor best practices."
alwaysApply: true
---
Spring WebFlux & Reactive Programming Principles:
- Prioritize non-blocking operations. Avoid block() calls in service or controller layers unless absolutely necessary.
- Embrace Mono for 0-1 element streams and Flux for 0-N element streams.
- Utilize Reactor operators (map, flatMap, filter, zip, onErrorResume, retryWhen, etc.) for data transformation and flow control.
- Ensure proper backpressure handling for long-running streams, if applicable.
- Design APIs to return reactive types (Mono<?>, Flux<?>).
- Error handling should use Reactor's built-in mechanisms (onErrorResume, doOnError) to maintain the reactive chain.
