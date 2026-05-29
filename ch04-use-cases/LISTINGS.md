# Chapter 4 — Listing Map

> Maps each code listing in chapter 4 to its source file in the submodules.

| Listing | Description | Source file |
|---------|-------------|-------------|
| 4.1 | PublishArticleUseCase — void handle (initial) | Conceptual progression — superseded by 4.13 |
| 4.2 | PublishArticleCommand with validateThenCreate (DomainError) | Conceptual progression — superseded by 4.7 |
| 4.3 | PublishArticleUseCase — Either return (honest signature) | Conceptual progression — superseded by 4.13 |
| 4.4 | Try-catch anti-pattern in controller | Conceptual — no source file |
| 4.5 | Either flow comparison | Conceptual — no source file |
| 4.6 | Sealed Error hierarchy | `reference-app/hexagonal-spring-ref-app/shared-kernel/src/main/java/.../shared/error/Error.java` + `.../shared/validation/ValidationError.java` |
| 4.7 | PublishArticleCommand with full Error type | Book-only — Ch9 builds this |
| 4.8 | Command and Query marker interfaces | `libs/architecture-kernel/command/src/main/java/com/emedina/sharedkernel/command/Command.java` + `libs/architecture-kernel/query/src/main/java/com/emedina/sharedkernel/query/Query.java` |
| 4.9 | PublishArticleHandler (basic) | Book-only — Ch9 builds this |
| 4.10 | PublishArticleHandler with @Transactional | Book-only — Ch9 builds this |
| 4.11 | CommandHandler interface | `libs/architecture-kernel/command-either-bus/src/main/java/com/emedina/sharedkernel/command/core/CommandHandler.java` |
| 4.12 | CommandBus interface | `libs/architecture-kernel/command-either-bus/src/main/java/com/emedina/sharedkernel/command/core/CommandBus.java` |
| 4.13 | PublishArticleUseCase extends CommandHandler | Book-only — Ch9 builds this |
| 4.14 | SpringCommandBus implementation | `libs/command-either-bus-spring-boot/src/main/java/com/emedina/command/spring/SpringCommandBus.java` |
| 4.15 | ArticleController (command endpoint) | `reference-app/hexagonal-spring-ref-app/api-adapter/src/main/java/.../api/ArticleController.java` |
| 4.16 | LoggingCommandBus decorator | `libs/architecture-kernel/command-either-bus/src/main/java/com/emedina/sharedkernel/command/decorator/LoggingCommandBus.java` |
| 4.17 | QueryHandler interface | `libs/architecture-kernel/query-either-bus/src/main/java/com/emedina/sharedkernel/query/core/QueryHandler.java` |
| 4.18 | QueryBus interface | `libs/architecture-kernel/query-either-bus/src/main/java/com/emedina/sharedkernel/query/core/QueryBus.java` |
| 4.19 | GetArticleByIdQuery with validateThenCreate | `reference-app/hexagonal-spring-ref-app/application-core/input-ports/src/main/java/.../application/query/FindArticleQuery.java` |
| 4.20 | GetArticleByIdUseCase extends QueryHandler | `reference-app/hexagonal-spring-ref-app/application-core/input-ports/src/main/java/.../application/ports/in/FindArticleUseCase.java` |
| 4.21 | GetArticleByIdHandler | `reference-app/hexagonal-spring-ref-app/application-core/application/src/main/java/.../application/FindArticleHandler.java` |
| 4.22 | ArticleController (query endpoint) | `reference-app/hexagonal-spring-ref-app/api-adapter/src/main/java/.../api/ArticleController.java` |
| 4.23 | Handler doing too much (anti-pattern) | Conceptual — no source file |
| 4.24 | ArticlePublished domain event record | Book-only — Ch9 builds this |
| 4.25 | Article entity with domain events | Book-only — Ch9 adds `publish()` + event list |
| 4.26 | Handler with domain event publishing | Book-only — Ch9 builds this |

## Notes

- Listings 4.1–4.3 show progressive refinement of the use case signature. Final form: 4.13.
- The `Registry` class used by `SpringCommandBus` is at `libs/command-either-bus-spring-boot/src/main/java/com/emedina/command/spring/Registry.java`.
- The `Timer` class used by `LoggingCommandBus` is at `libs/architecture-kernel/command-either-bus/src/main/java/com/emedina/sharedkernel/command/decorator/Timer.java`.
- PublishArticle use case is built from scratch in Chapter 9.
