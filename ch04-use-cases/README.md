# Chapter 4 — Use Cases and the Application Layer

This chapter introduces commands, queries, handlers, the sealed Error hierarchy, the bus pattern, and domain events.

## Repositories referenced

| Repository | What to look at |
|-----------|-----------------|
| [architecture-kernel](../libs/architecture-kernel/) | `command/`, `query/`, `command-bus/`, `command-either-bus/`, `query-bus/`, `query-either-bus/` modules |
| [command-either-bus-spring-boot](../libs/command-either-bus-spring-boot/) | Spring Boot auto-configuration for the Either-based Command Bus |
| [query-either-bus-spring-boot](../libs/query-either-bus-spring-boot/) | Spring Boot auto-configuration for the Either-based Query Bus |

## Key concepts

- Sealed `Error` hierarchy (BusinessError, TechnicalError, ValidationError)
- Commands and Queries with `validateThenCreate` returning `Either<Error, Self>`
- `CommandHandler<E, C>` and `QueryHandler<E, R, Q>` interfaces
- `CommandBus` and `QueryBus` dispatch contracts
- Decorator pattern (LoggingCommandBus)
- Domain events as records implementing `DomainEvent` marker

## Building

```bash
cd libs/architecture-kernel && mvn clean install
cd libs/command-either-bus-spring-boot && mvn clean install
cd libs/query-either-bus-spring-boot && mvn clean install
```

## Listing map

See [LISTINGS.md](LISTINGS.md) for the complete mapping of book listings to source files.
