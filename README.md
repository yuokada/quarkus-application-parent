# Quarkus Application Base
[![Maven Central Version](https://img.shields.io/maven-central/v/io.github.yuokada/quarkus-cli-application-base)](https://central.sonatype.com/artifact/io.github.yuokada/quarkus-cli-application-base)
[![Maven Central Version](https://img.shields.io/maven-central/v/io.github.yuokada/quarkus-server-application-base)](https://central.sonatype.com/artifact/io.github.yuokada/quarkus-server-application-base)



**Quarkus Application Base** is a foundational Maven parent POM that streamlines the development of Quarkus applications. 
It centralizes dependency and plugin management, enforces consistent configurations, and promotes best practices across multiple projects.

## Usage
This project serves as a template for creating Quarkus-based REST applications with a standardized structure and configuration.

### Client module

```xml
  <parent>
    <groupId>io.github.yuokada</groupId>
    <artifactId>quarkus-cli-application-base</artifactId>
    <version>${LATEST_VERSION}</version>
  </parent>
```

Extensions used in the client module:

- `quarkus-picocli`: For command-line interface (CLI) support.
- `quarkus-rest-client-jackson`: For JSON serialization and deserialization.
- `quarkus-smallrye-fault-tolerance`: For implementing fault tolerance patterns.

### Server module

```xml
  <parent>
    <groupId>io.github.yuokada</groupId>
    <artifactId>quarkus-server-application-base</artifactId>
    <version>${LATEST_VERSION}</version>
  </parent>
```

Extensions used in the server module:

- `quarkus-rest-jackson`: For JSON serialization and deserialization.
- `quarkus-smallrye-fault-tolerance`: For implementing fault tolerance patterns.
- `quarkus-logging-json`: For structured logging in JSON format.
- `quarkus-smallrye-openapi`: For generating OpenAPI documentation.
- `quarkus-smallrye-health`: For health checks and metrics.
- `quarkus-hibernate-validator`: For bean validation.


---

## 🚀 Features

- **Centralized Dependency Management**: Utilizes Quarkus BOM to ensure consistent versions across modules.
- **Plugin Management**: Defines common Maven plugins and configurations, reducing redundancy.
- **Standardized Build Configurations**: Sets default Java version, encoding, and other essential properties.
- **Multi-Module Support**: Facilitates the organization of complex projects with multiple modules.
- **Extensibility**: Easily extendable to accommodate project-specific needs.

---

## 📚 Resources

- [Quarkus Official Documentation](https://quarkus.io/guides/)
- [Quarkus Maven Plugin Guide](https://quarkus.io/guides/maven-tooling)
- [Creating Your First Quarkus Application](https://quarkus.io/guides/getting-started)

---

## 🤝 Contributing

Contributions are welcome! If you have suggestions or improvements, feel free to open an issue or submit a pull request.

---

## 📦 Release Procedure

Run the following commands on the `master` branch to cut a new release:

```bash
git checkout master
./mvnw -B release:clean release:prepare
git push --follow-tags
```

After the tags are pushed, GitHub Actions performs `mvn release:perform` to deploy
artifacts to Maven Central.

## ⏪ Rollback

If a release was created by mistake, undo it with:

```bash
git checkout master
./mvnw release:rollback
git tag -d <version>      # replace <version> with the tag to delete
git push --delete origin <version>
```

The final command removes the prepare commit so the repository returns to its
previous state.

---

## 📝 License

This project is licensed under the [MIT License](LICENSE).
