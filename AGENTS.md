# Repository Guidelines

This repository is a Maven multi-module that provides parent/base POMs for Quarkus applications. It enables consistent dependency and
plugin management to be reused across projects.

## Project Structure and Modules

- Root: pom.xml (parent/aggregator)
- Modules:
    - quarkus-cli-application-base/ (base POM for CLI apps)
    - quarkus-server-application-base/ (base POM for REST server apps)
- Aux: .mvn/, mvnw*, settings.xml, README.md

Downstream projects inherit these modules as their parent.

## Build, Test, and Development Commands

- Build and test all: ./mvnw -T 1C -q verify
- Local install: ./mvnw -q -DskipTests clean install
- Specific module only: ./mvnw -pl quarkus-cli-application-base -am verify
- Release preparation (see README): ./mvnw -B release:clean release:prepare && git push --follow-tags

Note: This repository itself does not contain runnable Quarkus apps (use mvn quarkus:dev in downstream projects).

## Coding Style and Naming

- XML formatting: 2-space indent; follow existing POM element/attribute order.
- Property naming: use clear scopes such as quarkus.platform.*.
- Artifact naming: follow quarkus-*-application-base.
- Prioritize avoiding breaking changes for downstream users.

## Testing Guidelines

- Always run mvn verify. Validate plugin/property changes across both modules.
- When possible, sanity-check with downstream sample projects.
- Avoid breaking changes (removing properties or changing defaults). If required, include migration notes in the PR.

## Commit and PR Guidelines

- Commits: concise imperative English. Examples: Add quarkus-logging-json to the CLI, Bump maven-deploy-plugin.
- PRs should include:
    - Purpose/background and impact (expected downstream effects)
    - What changed (key diffs; whether defaults changed)
    - Validation steps (Maven commands executed)
    - Related issues/screenshots (optional)

## Security and Configuration Notes

- Do not commit secrets (configure credentials in settings.xml).
- Keep OSSRH/GPG settings locally. Do not share .env.
