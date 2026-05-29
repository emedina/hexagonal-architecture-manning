# Chapter 7 — Enforcing the Architecture: ArchUnit as Executable Specification

This chapter covers ArchUnit rules that enforce hexagonal architecture at test time — dependency rules, annotation rules, structural rules, naming conventions, and the freeze mechanism.

## Repositories referenced

| Repository | What to look at |
|-----------|-----------------|
| [archunit-hexagonal](../libs/archunit-hexagonal/) | All checker classes, custom conditions, predicates, and test infrastructure |

## Key concepts

- Dependency enforcement: allowlists for inner layers, denylist for adapters
- Annotation enforcement: required (`@UseCase`, `@ApplicationService`), forbidden, allowed-or-none
- Structural enforcement: interfaces for ports, `validateThenCreate` contract, no public default constructors
- Generic type validation at parameterized positions
- Naming conventions: `XUseCase` → `XHandler`
- YAML-externalized configuration via `@ConfigurationProperties`
- `FreezingArchRule` for incremental adoption

## Building

```bash
cd libs/archunit-hexagonal && mvn clean install
```

## Listing map

See [LISTINGS.md](LISTINGS.md) for the complete mapping of book listings to source files.
