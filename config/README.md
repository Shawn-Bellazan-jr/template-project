# `config/` Directory

This directory contains configuration files and settings for the project. It includes Gradle build scripts and other configurations necessary for running the project.

## Structure

- `gradle/`: Contains Gradle wrapper scripts and additional Gradle configuration.
- `settings.gradle.kts`: Configures project-level settings and module inclusion.
- `build.gradle.kts`: The Kotlin DSL build script defining project dependencies, plugins, tasks, and settings.
- `dependencies.gradle.kts`: (Optional) Separate file for managing project dependencies.

## Guidelines

- Use environment variables for sensitive information like API keys and database credentials.
- Keep dependencies updated by using tools like Dependabot or Gradle Version Catalog.
- Organize build logic using buildSrc for custom tasks or plugin management.