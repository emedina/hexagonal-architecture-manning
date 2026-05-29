# Clean Hexagonal Architecture with Java and Spring Boot

Companion code for **Clean Hexagonal Architecture with Java and Spring Boot** (Manning Publications, forthcoming).

This repository organizes the book's source code — libraries, Spring Boot starters, ArchUnit rules, and the reference application — by chapter, with precise listing-to-file mappings.

**Publisher:** Manning Publications
**Repository:** https://github.com/emedina/hexagonal-architecture-manning

## Quick start

```bash
git clone --recursive https://github.com/emedina/hexagonal-architecture-manning.git
cd hexagonal-architecture-manning
```

If you already cloned without `--recursive`:

```bash
git submodule update --init --recursive
```

## Repository layout

```
hexagonal-architecture-manning/
├── libs/                              Shared libraries and Spring Boot starters
│   ├── architecture-kernel/           Annotations, markers, bus contracts, domain primitives
│   ├── command-bus-spring-boot/       Command Bus Spring Boot starter
│   ├── query-bus-spring-boot/         Query Bus Spring Boot starter
│   ├── command-either-bus-spring-boot/ Either-based Command Bus starter
│   ├── query-either-bus-spring-boot/  Either-based Query Bus starter
│   ├── transactional-either-spring-boot/ Either-aware @Transactional starter
│   └── archunit-hexagonal/           ArchUnit rules for hexagonal architecture
├── reference-app/
│   └── hexagonal-spring-ref-app/     Complete reference application (WriteFlow)
└── ch03-ch09 folders/                Per-chapter README + listing mappings
```

## Chapter-to-code mapping

| Chapter | Topic | Primary repositories | Folder |
|---------|-------|---------------------|--------|
| 3 | Building the Domain Core | [architecture-kernel](https://github.com/emedina/architecture-kernel) | [ch03-domain-core/](ch03-domain-core/) |
| 4 | Use Cases and the Application Layer | [architecture-kernel](https://github.com/emedina/architecture-kernel), [command-either-bus-spring-boot](https://github.com/emedina/command-either-bus-spring-boot), [query-either-bus-spring-boot](https://github.com/emedina/query-either-bus-spring-boot) | [ch04-use-cases/](ch04-use-cases/) |
| 5 | Adapters: Connecting the Hexagon | [hexagonal-spring-ref-app](https://github.com/emedina/hexagonal-spring-ref-app) | [ch05-adapters/](ch05-adapters/) |
| 6 | Assembly: Wiring the Hexagon | [transactional-either-spring-boot](https://github.com/emedina/transactional-either-spring-boot), [hexagonal-spring-ref-app](https://github.com/emedina/hexagonal-spring-ref-app) | [ch06-assembly/](ch06-assembly/) |
| 7 | Enforcing the Architecture: ArchUnit | [archunit-hexagonal](https://github.com/emedina/archunit-hexagonal) | [ch07-archunit/](ch07-archunit/) |
| 8 | Testing the Hexagon | [hexagonal-spring-ref-app](https://github.com/emedina/hexagonal-spring-ref-app) | [ch08-testing/](ch08-testing/) |
| 9 | Building WriteFlow: End-to-End | [hexagonal-spring-ref-app](https://github.com/emedina/hexagonal-spring-ref-app) | [ch09-writeflow/](ch09-writeflow/) |

## Prerequisites

- Java 21+
- Maven 3.9+
- Docker (optional, for integration tests)

## Building

Each submodule builds independently:

```bash
cd libs/architecture-kernel && mvn clean install
cd libs/command-either-bus-spring-boot && mvn clean install
cd libs/query-either-bus-spring-boot && mvn clean install
cd libs/transactional-either-spring-boot && mvn clean install
cd libs/archunit-hexagonal && mvn clean install
cd reference-app/hexagonal-spring-ref-app && mvn clean install
```

Or build everything in dependency order:

```bash
for lib in architecture-kernel command-bus-spring-boot query-bus-spring-boot \
           command-either-bus-spring-boot query-either-bus-spring-boot \
           transactional-either-spring-boot archunit-hexagonal; do
  (cd libs/$lib && mvn clean install -q) || exit 1
done
(cd reference-app/hexagonal-spring-ref-app && mvn clean install)
```

## About the book

This book is a practitioner's guide to implementing hexagonal architecture in Java with Spring Boot. Part I (chapters 3-9) builds the complete toolkit from domain modeling through architectural enforcement, testing, and a full end-to-end capstone. Every pattern is grounded in production-tested code.

## Related repositories

| Repository | Description |
|-----------|-------------|
| [architecture-kernel](https://github.com/emedina/architecture-kernel) | Shared kernel: annotations, markers, bus interfaces, domain primitives |
| [command-bus-spring-boot](https://github.com/emedina/command-bus-spring-boot) | Spring Boot auto-configuration for the basic Command Bus |
| [query-bus-spring-boot](https://github.com/emedina/query-bus-spring-boot) | Spring Boot auto-configuration for the basic Query Bus |
| [command-either-bus-spring-boot](https://github.com/emedina/command-either-bus-spring-boot) | Spring Boot auto-configuration for the Either-based Command Bus |
| [query-either-bus-spring-boot](https://github.com/emedina/query-either-bus-spring-boot) | Spring Boot auto-configuration for the Either-based Query Bus |
| [transactional-either-spring-boot](https://github.com/emedina/transactional-either-spring-boot) | Either-aware `@Transactional` Spring Boot starter |
| [archunit-hexagonal](https://github.com/emedina/archunit-hexagonal) | ArchUnit rules for validating hexagonal architecture |
| [hexagonal-spring-ref-app](https://github.com/emedina/hexagonal-spring-ref-app) | Complete reference application (WriteFlow) |
