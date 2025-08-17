---
description: "Core principles for reactive programming with Project Reactor."
alwaysApply: true
---
Reactive Programming Fundamentals:
- Embrace Mono for zero-or-one element sequences and Flux for zero-to-many element sequences from Project Reactor.
- Prefer Reactor operators (map, flatMap, filter, doOnNext, onErrorResume, retryWhen, zip, combineLatest, etc.) for all data transformations and flow control.
- Avoid blocking calls (.block(), .get()) in reactive chains. Offload blocking to Scheduler.boundedElastic() if unavoidable.
- Error handling must be explicit and reactive, typically using onErrorResume, doOnError, or custom error handlers.
- Design methods to return reactive types (Mono_ or Flux_) to propagate reactivity throughout the service.
- Use Duration for timeouts and delays, avoiding Thread.sleep().
