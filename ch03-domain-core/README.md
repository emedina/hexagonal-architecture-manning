# Chapter 3 — Building the Domain Core

This chapter introduces the always-valid domain model, value objects, domain services, and factories using the Architecture Kernel's domain primitives.

## Repositories referenced

| Repository | What to look at |
|-----------|-----------------|
| [architecture-kernel](../libs/architecture-kernel/) | `domain/` module — `@DomainEntity`, `@DomainService`, `@ValueObject`, `@Identity`, `@Factory` annotations |

## Key concepts

- Always-valid domain model via `validateThenCreate` factory methods
- Value objects as Java records with compact constructor validation
- Domain services for cross-aggregate logic
- Factory pattern for complex entity construction
- `Validation<Seq<DomainError>, T>` for error accumulation

## Building

```bash
cd libs/architecture-kernel
mvn clean install
```

## Listing map

See [LISTINGS.md](LISTINGS.md) for the complete mapping of book listings to source files.
