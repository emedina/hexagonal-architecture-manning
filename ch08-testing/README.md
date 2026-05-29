# Chapter 8 — Testing the Hexagon: Behavioural Verification

This chapter covers the mechanical, deterministic unit testing recipes for every artifact type in the hexagon.

## Repositories referenced

| Repository | What to look at |
|-----------|-----------------|
| [hexagonal-spring-ref-app](../reference-app/hexagonal-spring-ref-app/) | Test sources in each module (`src/test/java/`) |

## Key concepts

- BDD structure: `// given` / `// when` / `// then` inline comments
- `@DisplayName` on all test methods for readable intent
- Flat methods only (no `@Nested`)
- Command/Query recipe: valid creation + parameterized invalid inputs
- Handler recipe: mock ports, stub responses, verify interactions
- Controller recipe: mock bus + error handler, assert HTTP responses
- Adapter recipes: persistence (mock Spring Data), cache (real impl), OpenAPI (`mockConstruction`), HTTP (`MockRestServiceServer`)
- Import convention: `BDDAssertions.then` + `BDDMockito.given`

## Building

```bash
cd reference-app/hexagonal-spring-ref-app && mvn test
```

## Listing map

See [LISTINGS.md](LISTINGS.md) for the complete mapping of book listings to source files.
