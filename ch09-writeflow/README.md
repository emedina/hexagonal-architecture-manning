# Chapter 9 — Building WriteFlow: End-to-End Construction

This chapter is the Part I capstone — a guided inside-out construction of the complete PublishArticle command and GetArticleById query use cases, applying every pattern from chapters 3 through 8.

## Repositories referenced

| Repository | What to look at |
|-----------|-----------------|
| [hexagonal-spring-ref-app](../reference-app/hexagonal-spring-ref-app/) | The complete application: domain, ports, handlers, adapters, assembly |

## What this chapter builds

| Layer | Artifacts |
|-------|-----------|
| Domain | `Article`, `ArticleId`, `Title`, `Content`, `AuthorId`, `ArticleStatus`, `ArticlePublished` |
| Input Ports | `PublishArticleUseCase`, `GetArticleByIdUseCase` |
| Output Ports | `ArticleRepository`, `DomainEventPublisherPort` |
| Commands/Queries | `PublishArticleCommand`, `GetArticleByIdQuery` |
| Handlers | `PublishArticleHandler`, `GetArticleByIdHandler` |
| Adapters | `JpaArticleRepository`, `SpringDomainEventPublisher`, `ArticleController` |
| Event consumers | `NotifySubscribersOnArticlePublished`, `ArticlePublishedOutboxWriter` |
| Assembly | Module wiring via `spring-boot-assembly` |

## Running the reference app

```bash
cd reference-app/hexagonal-spring-ref-app
mvn clean install
cd spring-boot-assembly
mvn spring-boot:run
```

## Listing map

See [LISTINGS.md](LISTINGS.md) for the complete mapping of book listings to source files.
