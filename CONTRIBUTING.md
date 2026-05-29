# Contributing

Thanks for your interest in improving this code repository.

This repo holds the companion code that accompanies the book *Clean Hexagonal Architecture with Java and Spring Boot* (Manning). Code contributions are welcome. Book content (prose, figures, structure) is owned by Manning Publications and is not part of this repo — for book content please use [Manning's liveBook forum](https://livebook.manning.com/) instead of opening a pull request here.

## What we welcome

- Bug fixes in library or reference application code
- README clarifications when a step is unclear or out of date
- Listing mapping corrections (wrong file path, outdated line number)
- Build fixes for newer JDK or Maven versions
- Test improvements that cover an existing module more thoroughly

## What we don't accept

- Rewrites of the book's prose or examples (those live in the manuscript at Manning)
- Sweeping refactors that change the module structure (the book references modules by name)
- Adding new libraries or replacing the existing technology choices
- Changes to submodule references without corresponding upstream changes

## Structure

This is a meta-repository. Source code lives in the submodule repositories:

- Library fixes → open a PR on the specific library repo (e.g., [architecture-kernel](https://github.com/emedina/architecture-kernel))
- Reference app fixes → open a PR on [hexagonal-spring-ref-app](https://github.com/emedina/hexagonal-spring-ref-app)
- Listing mapping or README fixes → open a PR here

## Development setup

```bash
git clone --recursive https://github.com/emedina/hexagonal-architecture-manning.git
cd hexagonal-architecture-manning
```

Build all libraries in order:

```bash
for lib in architecture-kernel command-bus-spring-boot query-bus-spring-boot \
           command-either-bus-spring-boot query-either-bus-spring-boot \
           transactional-either-spring-boot archunit-hexagonal; do
  (cd libs/$lib && mvn clean install -q) || exit 1
done
(cd reference-app/hexagonal-spring-ref-app && mvn clean install)
```

Requires Java 21+ and Maven 3.9+.
