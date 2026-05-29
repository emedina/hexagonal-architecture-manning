# Chapter 5 — Listing Map

> Maps each code listing in chapter 5 to its source file in the submodules.

| Listing | Description | Source file |
|---------|-------------|-------------|
| 5.1 | ErrorResponseMapper (@RestControllerAdvice) | `reference-app/hexagonal-spring-ref-app/api-adapter/src/main/java/.../api/ApiErrorHandler.java` + `ApiGlobalExceptionHandler.java` |
| 5.2 | Header interface (anti-pattern) | Conceptual — no source file |
| 5.3 | Role interface with @OutputPort | `reference-app/hexagonal-spring-ref-app/application-core/output-ports/src/main/java/.../ports/out/AuthorOutputPort.java` |
| 5.4 | EmailNotificationAdapter | Conceptual — book-only (notification pattern) |
| 5.5 | DTOs as records | `reference-app/hexagonal-spring-ref-app/shared-kernel/src/main/java/.../shared/dto/ArticleDTO.java` + `AuthorDTO.java` |
| 5.6 | ArticleRepository (domain-owned port) | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/repositories/ArticleRepository.java` |
| 5.7 | Anti-pattern: domain port extends Spring Data | Conceptual — no source file |
| 5.8 | SpringArticleRepository (adapter-internal) | Conceptual — ref app uses in-memory |
| 5.9 | JpaArticleRepository adapter | Pattern demonstrated by `reference-app/hexagonal-spring-ref-app/in-memory-repositories/src/main/java/.../repositories/InMemoryArticleRepository.java` |
| 5.10 | ArticlePersistenceMapper | `reference-app/hexagonal-spring-ref-app/application-core/application/src/main/java/.../application/ArticleMapper.java` |
| 5.11 | ArticleController anti-pattern (no mapping) | Conceptual — no source file |
| 5.12 | GetArticleByIdHandler (one-way mapping) | `reference-app/hexagonal-spring-ref-app/application-core/application/src/main/java/.../application/FindArticleHandler.java` |
| 5.13 | JpaArticle persistence entity | Conceptual — ref app uses in-memory |
| 5.14 | ArticleController (Full Bridge) | `reference-app/hexagonal-spring-ref-app/api-adapter/src/main/java/.../api/ArticleController.java` |
| 5.15 | PublicationReadinessHandler | Conceptual — book-only |

## Notes

- The reference app uses `InMemoryArticleRepository` rather than JPA. The JPA pattern (5.8, 5.9, 5.13) is taught conceptually.
- The external service adapter pattern (5.4) is demonstrated by `reference-app/hexagonal-spring-ref-app/author-external-adapter/src/main/java/.../external/AuthorExternalAPIAdapter.java`.
