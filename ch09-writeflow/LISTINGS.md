# Chapter 9 — Listing Map

> Maps each code listing in chapter 9 to its source file in the submodules.
> Chapter 9 is the capstone — it builds PublishArticle and GetArticleById end-to-end.

| Listing | Description | Source file |
|---------|-------------|-------------|
| 9.1 | Value objects (ArticleId, Title, Content, AuthorId, ArticleStatus) | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/entities/ArticleId.java`, `Title.java`, `Content.java`, `AuthorId.java` |
| 9.2 | Article entity with validateThenCreate | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/entities/Article.java` |
| 9.3 | Article.publish() with domain event registration | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/entities/Article.java` |
| 9.4 | ArticlePublished domain event | Book-only — to be added to reference app |
| 9.5 | PublishArticleUseCase and GetArticleByIdUseCase | `reference-app/hexagonal-spring-ref-app/application-core/input-ports/src/main/java/.../ports/in/FindArticleUseCase.java` (GetArticleById pattern) |
| 9.6 | ArticleRepository with CQRS split | `reference-app/hexagonal-spring-ref-app/application-core/domain/src/main/java/.../domain/repositories/ArticleRepository.java` |
| 9.7 | PublishArticleCommand with validateThenCreate | Pattern shown in `reference-app/hexagonal-spring-ref-app/application-core/input-ports/src/main/java/.../command/CreateArticleCommand.java` |
| 9.8 | GetArticleByIdQuery with validateThenCreate | `reference-app/hexagonal-spring-ref-app/application-core/input-ports/src/main/java/.../query/FindArticleQuery.java` |
| 9.9 | PublishArticleHandler (flatMap chain) | Book-only — to be added to reference app |
| 9.10 | GetArticleByIdHandler | `reference-app/hexagonal-spring-ref-app/application-core/application/src/main/java/.../application/FindArticleHandler.java` |
| 9.11 | JpaArticleRepository (persistence adapter) | Pattern in `reference-app/hexagonal-spring-ref-app/in-memory-repositories/src/main/java/.../repositories/InMemoryArticleRepository.java` |
| 9.12 | ArticlePersistenceMapper | `reference-app/hexagonal-spring-ref-app/application-core/application/src/main/java/.../application/ArticleMapper.java` |
| 9.13 | JpaArticle + SpringArticleRepository | Conceptual — ref app uses in-memory |
| 9.14 | SpringDomainEventPublisher | Book-only — to be added to reference app |
| 9.15 | NotifySubscribersOnArticlePublished (event listener) | Book-only — to be added to reference app |
| 9.16 | ArticlePublishedOutboxWriter | Book-only — to be added to reference app |
| 9.17 | ArticleController (command + query endpoints) | `reference-app/hexagonal-spring-ref-app/api-adapter/src/main/java/.../api/ArticleController.java` |
| 9.18 | Module POM dependencies (assembly wiring) | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/pom.xml` |

## Sequence diagrams

- **Figure 9.2** — PublishArticle command flow (Controller → Bus → Handler → Repository → EventPublisher)
- **Figure 9.3** — Event consumption flow (ArticlePublished → NotifySubscribers + OutboxWriter)
- **Figure 9.4** — GetArticleById query flow (Controller → Bus → Handler → Repository → DTO)

## Notes

- Several Ch9 listings represent code to be added to the reference app as part of the capstone exercise.
- The existing reference app has CreateArticle, DeleteArticle, UpdateArticle, FindArticle, GetAllArticles — PublishArticle is the Ch9 addition.
- "Book-only" items will be added to the reference app once Ch9 manuscript is finalized.
