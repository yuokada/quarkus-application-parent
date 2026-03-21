# GitHub Copilot Instructions

Follow these repository instructions when working in this project.

## General guidance

- Keep changes focused and consistent with the current Maven multi-module parent POM design.
- Write new or updated repository instructions, comments, and documentation in English.
- Avoid local absolute paths, machine-specific assumptions, and committed secrets.
- Preserve compatibility for downstream projects that inherit these parent POMs.
- Prefer additive or minimally disruptive changes over changes that alter defaults without a clear reason.

## Project context

- The root `pom.xml` is the parent and aggregator for the repository.
- `quarkus-cli-application-base/` defines the CLI-focused base POM.
- `quarkus-server-application-base/` defines the server-focused base POM.
- Release and publishing workflows live under `.github/workflows/`.

## Validation

- Prefer `./mvnw -q verify` when parent POM behavior or module configuration changes.
- Prefer module-scoped verification when only one child module is affected.
- Clearly distinguish between checks you ran and checks you did not run.
