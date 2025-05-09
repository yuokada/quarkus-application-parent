# Quarkus Application Base
[![Maven Central Version](https://img.shields.io/maven-central/v/io.github.yuokada/quarkus-application-base)](https://central.sonatype.com/artifact/io.github.yuokada/quarkus-application-base)



**Quarkus Application Base** is a foundational Maven parent POM that streamlines the development of Quarkus applications. 
It centralizes dependency and plugin management, enforces consistent configurations, and promotes best practices across multiple projects.

## Usage
This project serves as a template for creating Quarkus-based REST applications with a standardized structure and configuration.

```xml
  <parent>
    <groupId>io.github.yuokada</groupId>
    <artifactId>quarkus-application-base</artifactId>
    <version>${LATEST_VERSION}</version>
  </parent>
```

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

## 📝 License

This project is licensed under the [MIT License](LICENSE).

---

Feel free to modify this `README.md` to better suit your project's specifics or to add more detailed instructions as needed. 
