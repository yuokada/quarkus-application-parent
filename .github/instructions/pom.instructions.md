---
applyTo:
  - "pom.xml"
  - "quarkus-cli-application-base/pom.xml"
  - "quarkus-server-application-base/pom.xml"
---

When editing Maven POM files in this repository:

- Keep parent properties, plugin management, and dependency management consistent across modules.
- Avoid breaking downstream consumers by removing properties, changing coordinates, or changing defaults without clear justification.
- Prefer changes that work for both child modules unless the change is intentionally module-specific.
- Keep release and publishing configuration aligned with the existing Maven Central workflow.
