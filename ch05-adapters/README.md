# Chapter 5 — Adapters: Connecting the Hexagon

This chapter covers input adapters (REST controllers), output adapters (persistence, external services), the mapping journey, and DTOs.

## Repositories referenced

| Repository | What to look at |
|-----------|-----------------|
| [hexagonal-spring-ref-app](../reference-app/hexagonal-spring-ref-app/) | `api-adapter/` (REST input), `in-memory-repositories/` (persistence output), `author-external-adapter/` (external service output) |

## Key concepts

- Role interfaces vs. header interfaces (`@OutputPort`)
- Repository adapter pattern (domain port + Spring Data delegation + mapper)
- Mapping journey: no mapping → one-way → two-way → full bridge
- Error-to-HTTP mapping via `@RestControllerAdvice`
- `@Adapter` stereotype annotation

## Building

```bash
cd libs/architecture-kernel && mvn clean install
cd reference-app/hexagonal-spring-ref-app && mvn clean install
```

## Listing map

See [LISTINGS.md](LISTINGS.md) for the complete mapping of book listings to source files.
