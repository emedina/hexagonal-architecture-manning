# Chapter 7 — Listing Map

> Maps each code listing in chapter 7 to its source file in the submodules.

| Listing | Description | Source file |
|---------|-------------|-------------|
| 7.1 | HexagonalArchitectureProperties (configuration record) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/config/HexagonalArchitectureProperties.java` |
| 7.2 | HexagonalArchitectureConfig (activation) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/config/HexagonalArchitectureConfig.java` |
| 7.3 | WriteFlow's ArchUnit YAML configuration | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/test/resources/` (application-test.yaml or similar) |
| 7.4 | SharedKernelChecker (dependency enforcement) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/sharedkernel/SharedKernelChecker.java` |
| 7.5 | Domain dependency rule | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/domain/DomainChecker.java` |
| 7.6 | Handler dependency rule | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/handler/HandlerChecker.java` |
| 7.7 | AdapterChecker (inverse dependency enforcement) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/adapters/AdapterChecker.java` |
| 7.8 | CommandChecker (forbidden annotations) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/command/CommandChecker.java` |
| 7.9 | InputPortChecker (required annotation) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/ports/in/InputPortChecker.java` |
| 7.10 | OutputPortChecker (required annotation) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/ports/out/OutputPortChecker.java` |
| 7.11 | HandlerChecker (required @ApplicationService) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/handler/HandlerChecker.java` |
| 7.12 | DomainChecker (allowed annotations or none) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/domain/DomainChecker.java` |
| 7.13 | DomainChecker annotation allowlist rule | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/domain/DomainChecker.java` |
| 7.14 | InputPort/OutputPort must be interfaces | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/ports/in/InputPortChecker.java` |
| 7.15 | CommandChecker (marker interface requirement) | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/command/CommandChecker.java` |
| 7.16 | Custom condition: validateThenCreate enforcement | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/command/CommandChecker.java` |
| 7.17 | CommandChecker factory method rule | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/command/CommandChecker.java` |
| 7.18 | Custom condition: no public default constructor | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/command/CommandChecker.java` |
| 7.19 | CommandChecker no default constructor rule | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/command/CommandChecker.java` |
| 7.20 | Generic type validation at specific position | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/ports/in/InputPortChecker.java` |
| 7.21 | InputPortChecker generic type rules | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/ports/in/InputPortChecker.java` |
| 7.22 | Custom predicate: implementUseCaseInterface | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/handler/HandlerChecker.java` |
| 7.23 | Custom condition: UseCase naming convention | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/handler/HandlerChecker.java` |
| 7.24 | HandlerChecker naming convention rule | `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/handler/HandlerChecker.java` |
| 7.25 | SharedKernelArchitectureTest | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/test/java/.../SharedKernelArchitectureTest.java` |
| 7.26 | HandlerArchitectureTest | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/test/java/.../HandlerArchitectureTest.java` |
| 7.27 | AdaptersArchitectureTest | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/test/java/.../AdaptersArchitectureTest.java` |
| 7.28 | FreezingArchRule pattern | Inside any checker class (`FreezingArchRule.freeze(rule).check(classes)`) |
| 7.29 | archunit.properties (freeze configuration) | `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/test/resources/archunit.properties` |

## Notes

- The `QueryChecker` mirrors `CommandChecker` at `libs/archunit-hexagonal/src/main/java/com/emedina/hexagonal/application/query/QueryChecker.java`.
- All architecture test classes live in `reference-app/hexagonal-spring-ref-app/spring-boot-assembly/src/test/java/com/emedina/hexagonal/ref/app/`:
  - `SharedKernelArchitectureTest.java`
  - `DomainArchitectureTest.java`
  - `CommandArchitectureTest.java`
  - `QueryArchitectureTest.java`
  - `InputPortsArchitectureTest.java`
  - `OutputPortsArchitectureTest.java`
  - `HandlerArchitectureTest.java`
  - `AdaptersArchitectureTest.java`
