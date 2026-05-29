# Chapter 6 — Assembly: Wiring the Hexagon

This chapter covers module organization, DI wiring, the Either-aware `@Transactional` bridge, domain events, integration events, and the outbox pattern.

## Repositories referenced

| Repository | What to look at |
|-----------|-----------------|
| [transactional-either-spring-boot](../libs/transactional-either-spring-boot/) | Either-aware transaction interceptor and annotation |
| [hexagonal-spring-ref-app](../reference-app/hexagonal-spring-ref-app/) | `spring-boot-assembly/` module, `application-core/` POM structure |
| [architecture-kernel](../libs/architecture-kernel/) | `transactional/` module — `@Transactional` annotation definition |

## Key concepts

- Maven multi-module structure (parent → shared-kernel, application-core, adapters, assembly)
- `@ComponentScan` with Architecture Kernel stereotype filters
- `CommandQueryBusAssembler` and `Registry` pattern
- Either-aware `@Transactional` — rollback by value, not exception
- Domain event publishing via Spring `ApplicationEventPublisher`
- `@TransactionalEventListener(phase = AFTER_COMMIT)` consumers
- Integration events and the outbox table pattern

## Building

```bash
cd libs/transactional-either-spring-boot && mvn clean install
cd reference-app/hexagonal-spring-ref-app && mvn clean install
```

## Listing map

See [LISTINGS.md](LISTINGS.md) for the complete mapping of book listings to source files.
