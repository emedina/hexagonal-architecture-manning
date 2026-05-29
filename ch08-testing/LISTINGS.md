# Chapter 8 — Listing Map

> Maps each code listing in chapter 8 to its source file in the submodules.

| Listing | Description | Source file |
|---------|-------------|-------------|
| 8.1 | BDD structure applied to every unit test | Pattern — all test files follow this |
| 8.2 | @DisplayName for readable test intent | Pattern — all test files follow this |
| 8.3 | BDD import convention (BDDAssertions + BDDMockito) | Pattern — all test files follow this |
| 8.4 | Testing valid command creation | `reference-app/hexagonal-spring-ref-app/application-core/input-ports/src/test/java/.../command/CreateArticleCommandTest.java` |
| 8.5 | Testing invalid command creation (parameterized) | `reference-app/hexagonal-spring-ref-app/application-core/input-ports/src/test/java/.../command/CreateArticleCommandTest.java` |
| 8.6 | PublishArticleHandlerTest scaffold | Book-only — Ch9 builds this use case |
| 8.7 | Handler happy path: stub ports, call handle, assert right | `reference-app/hexagonal-spring-ref-app/application-core/application/src/test/java/.../application/CreateArticleHandlerTest.java` (pattern) |
| 8.8 | Handler not-found path: assert left, verify no save | `reference-app/hexagonal-spring-ref-app/application-core/application/src/test/java/.../application/FindArticleHandlerTest.java` (pattern) |
| 8.9 | Handler persistence failure: error propagation | `reference-app/hexagonal-spring-ref-app/application-core/application/src/test/java/.../application/CreateArticleHandlerTest.java` (pattern) |
| 8.10 | ArticleControllerTest scaffold | `reference-app/hexagonal-spring-ref-app/api-adapter/src/test/java/.../api/ArticleControllerTest.java` |
| 8.11 | Controller happy path: bus succeeds, 201 | `reference-app/hexagonal-spring-ref-app/api-adapter/src/test/java/.../api/ArticleControllerTest.java` |
| 8.12 | Controller bus failure: error handler maps response | `reference-app/hexagonal-spring-ref-app/api-adapter/src/test/java/.../api/ArticleControllerTest.java` |
| 8.13 | Controller query path: bus returns data, 200 | `reference-app/hexagonal-spring-ref-app/api-adapter/src/test/java/.../api/ArticleControllerTest.java` |
| 8.14 | Persistence adapter test (mock Spring Data) | `reference-app/hexagonal-spring-ref-app/in-memory-repositories/src/test/java/.../repositories/InMemoryArticleRepositoryTest.java` |
| 8.15 | Cache adapter test (real implementation) | Conceptual — book-only |
| 8.16 | OpenAPI client adapter (mockConstruction) | `reference-app/hexagonal-spring-ref-app/author-external-adapter/src/test/java/.../external/AuthorExternalAPIAdapterTest.java` |
| 8.17 | RestClient adapter (MockRestServiceServer) | Conceptual — book-only |

## Notes

- Listings 8.1–8.3 are structural patterns, not individual files. Every test in the reference app follows these conventions.
- The PublishArticle handler tests (8.6–8.9) use the pattern visible in `CreateArticleHandlerTest`, `DeleteArticleHandlerTest`, `FindArticleHandlerTest`, etc.
- Cache and RestClient adapter tests (8.15, 8.17) are conceptual patterns not present in the reference app.
