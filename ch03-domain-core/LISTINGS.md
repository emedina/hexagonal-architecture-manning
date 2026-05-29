# Chapter 3 — Listing Map

> Maps each code listing in chapter 3 to its source file in the submodules.

| Listing | Description | Source file |
|---------|-------------|-------------|
| 3.1 | First create, then validate (anti-pattern) | Conceptual — no source file |
| 3.2 | Validation logic in the handler (anti-pattern) | Conceptual — no source file |
| 3.3 | Factory method enforcing validation in construction | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/entities/Article.java` |
| 3.4 | Invalid fields returned as errors to the user | Usage example of `Article.validateThenCreate` |
| 3.5 | Validated creation of an article inside a handler | `reference-app/hexagonal-spring-ref-app/application-core/application/src/main/java/.../application/CreateArticleHandler.java` |
| 3.6 | Unit test for article enforcing the Always-Valid Model | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/test/java/.../domain/entities/ArticleTest.java` |
| 3.7 | Separating validation from construction (canBeCreated) | Conceptual variant — not in final source |
| 3.8 | Constructor validation using exceptions | Conceptual variant — not in final source |
| 3.9 | Value objects as Java records | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/entities/Title.java`, `ArticleId.java`, `Content.java` |
| 3.10 | Primitive obsession vs explicit types | Conceptual contrast — no dedicated file |
| 3.11 | Multi-field value object (PublicationPeriod) | Conceptual example — book-only |
| 3.12 | Domain service: SlugUniquenessService | Conceptual example — book-only |
| 3.13 | Unit testing a domain service | Conceptual example — book-only |
| 3.14 | Factory for complex entity construction | Conceptual example — book-only |
| 3.15 | Value object with in-scope identity | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/entities/ArticleId.java` |
| 3.16 | Repository interface with nextIdentity | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/repositories/ArticleRepository.java` |
| 3.17 | Command with validateThenCreate | `reference-app/hexagonal-spring-ref-app/application-core/input-ports/src/main/java/.../application/command/CreateArticleCommand.java` |
| 3.18 | Guard clauses for intent clarity | Conceptual example — book-only |

## Notes

- Listings 3.1, 3.2, 3.7, 3.8 are anti-patterns or alternative approaches shown for contrast.
- Listings 3.11–3.14 are conceptual examples that teach patterns without a dedicated source file.
- The canonical domain entity implementation is in `reference-app/hexagonal-spring-ref-app/application-core/domain/`.
