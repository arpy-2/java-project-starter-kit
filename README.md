# Java Starter Kit: Technical Guide

This guide explains how the `pom.xml` file organizes the project. Think of it as the **instruction manual** that tells Maven how to build the application and what tools to use.

---

### 1. Project Setup (Environment)
These settings ensure the code works the same way on everyone's computer:

*   **Java Version:** We use **Java 17**. This setting tells the computer to use modern Java features to compile and run the code.
*   **Encoding (UTF-8):** This ensures that special characters (like accents or symbols) are displayed correctly in any operating system.
*   **Version Control:** We use variables (like `${lombok.version}`) to manage library versions in one single place, making it easier to update them later.

---

### 2. Tools & Libraries (Dependencies)
Dependencies are external "toolkits" we add to the project so we don't have to code everything from scratch:

*   **Logging (SLF4J + Log4j2):** Instead of using simple print statements, we use these professional tools to record what happens in the app (errors, info, warnings).
*   **Lombok:** A "shortcut" library. It automatically creates common code like Getters and Setters, keeping our files clean and short.
*   **Testing Suite (JUnit 5 & Mockito):** 
    *   **JUnit:** The standard tool for checking if our code works as expected.
    *   **Mockito:** Allows us to create "fake" objects to test specific parts of the code without needing a real database or server.

> [!TIP]
> **What is "Scope"?** 
> Some tools are only needed for testing (Scope: `test`) and won't be included when we launch the app to production. This keeps the final app lightweight.

---

### 3. Automation (Plugins)
Plugins are like "robots" that perform repetitive tasks automatically:

*   **Surefire Plugin:** This "robot" automatically runs all your tests every time you build the project to make sure nothing is broken.
*   **Build Process:** Handles the heavy lifting of turning your source code into a professional package ready to be shared.

---
