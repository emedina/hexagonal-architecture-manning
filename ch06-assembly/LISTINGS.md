# Chapter 6 — Listing Map

> Maps each code listing in chapter 6 to its source file in the submodules.

| Listing | Description | Source file |
|---------|-------------|-------------|
| 6.1 | Parent POM with module declarations | `reference-app/hexagonal-spring-ref-app/pom.xml` |
| 6.2 | Application-core sub-module POM | `reference-app/hexagonal-spring-ref-app/application-core/pom.xml` |
| 6.3 | Application bootstrap class | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/main/java/.../Application.java` |
| 6.4 | ApplicationAssembler (stereotype scanning) | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/main/java/.../assembly/ApplicationAssembler.java` |
| 6.5 | CommandQueryBusAssembler | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/main/java/.../assembly/CommandQueryBusAssembler.java` |
| 6.6 | InfrastructureAssembler | Conceptual — book-only (ref app doesn't have external infra beans) |
| 6.7 | @Transactional annotation definition | `libs/architecture-kernel/transactional/src/main/java/com/emedina/sharedkernel/transactional/Transactional.java` |
| 6.8 | TransactionManagerConfigWithEither | `libs/transactional-either-spring-boot/src/main/java/com/emedina/transactional/config/TransactionManagerConfigWithEither.java` |
| 6.9 | TransactionInterceptorWithEither (Either left inspection) | `libs/transactional-either-spring-boot/src/main/java/com/emedina/transactional/support/TransactionInterceptorWithEither.java` |
| 6.10 | GetArticleByIdHandler with @Transactional(readOnly) | `reference-app/hexagonal-spring-ref-app/application-core/application/src/main/java/.../application/FindArticleHandler.java` |
| 6.11 | SpringDomainEventPublisher | Book-only — Ch9 builds this |
| 6.12 | NotifySubscribersOnArticlePublished (event listener) | Book-only — Ch9 builds this |
| 6.13 | ArticlePublishedIntegrationEvent record | Book-only — Ch9 builds this |
| 6.14 | Integration event outbox table (SQL) | Book-only — Ch9 builds this |

## Notes

- The `@Transactional` annotation has supporting enums at:
  - `libs/architecture-kernel/transactional/src/main/java/.../transactional/Propagation.java`
  - `libs/architecture-kernel/transactional/src/main/java/.../transactional/Isolation.java`
- The Either-aware transaction bridge has additional support classes at `libs/transactional-either-spring-boot/src/main/java/com/emedina/transactional/support/`:
  - `SpringTransactionAnnotationParserWithEither.java`
  - `TransactionAspectSupportWithEither.java`
  - `DelegatingTransactionAttributeWithEither.java`
  - `RuleBasedTransactionAttributeWithEither.java`
