# Technical Specification: `pom.xml`

The `pom.xml` file serves as the project's **declarative configuration**, managing the build lifecycle, environment properties, and dependency resolution.

<br/>

---

<br/>

### 1. Build Environment & Properties
We leverage Maven properties to ensure build reproducibility and cross-platform compatibility:

*   **Java Roadmap:** Configured with `maven.compiler.source` and `target` to enforce the **Java 17+** bytecode version.
*   **Encoding:** Global use of `UTF-8` via `project.build.sourceEncoding` to prevent character corruption across different OS environments.
*   **Dependency Management:** Centralized versioning (e.g., `${lombok.version}`) to maintain consistency across the dependency tree.

<br/>

---

<br/>

### 2. Dependency Architecture
The project utilizes a curated stack of industry-standard libraries:

*   **Logging Layer:** `SLF4J` abstraction with `Log4j2` implementation for high-performance, asynchronous logging.
*   **Boilerplate Reduction:** `Project Lombok` for cleaner POJOs, utilizing compile-time annotation processing.
*   **Testing Suite:**
    *   **JUnit 5 (Jupiter):** Modern testing engine for unit and integration tests.
    *   **Mockito:** Behavioral testing through robust mocking and verification.
    *   **Mockito-JUnit-Jupiter:** Seamless integration to manage mock lifecycles automatically.


> [!NOTE]
> **On Scopes:** We strictly follow Maven scopes (`test`, `provided`) to minimize the final artifact size and prevent classpath pollution in production.

<br/>

---

<br/>

### 3. Build Plugins & Lifecycle
*   **Maven Surefire Plugin:** Integrated into the `test` phase to automate the execution of the testing suite and generate XML/HTML reports.
*   **Resource Management:** Automated handling of project resources and compiler optimizations during the `package` phase.
