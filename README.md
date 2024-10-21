# Kotlin DSL Gradle Project Template
![Build Status](https://github.com/Shawn-Bellazan-jr/template-project/actions/workflows/ci.yml/badge.svg)

This is a template project using **Kotlin DSL** for Gradle. It demonstrates how to structure a Kotlin project, use Kotlin Gradle DSL for configuration, and includes a custom build logic module for shared build configuration.

## Table of Contents
- [Directory Structure](#directory-structure)
- [Project Setup](#project-setup)
- [Building the Project](#building-the-project)
- [Running Tests](#running-tests)
- [Dependency Management](#dependency-management)
- [Custom Build Logic](#custom-build-logic)
- [Continuous Integration](#continuous-integration)
- [Contribution Guidelines](#contribution-guidelines)
- [License](#license)

## Directory Structure

This template is organized as follows:

```
template-project/
├── app/                # Main application module
│   ├── build.gradle.kts
│   └── src/
├── ui/                 # UI module (subproject)
│   ├── build.gradle.kts
│   └── src/
├── utilities/          # Utility services module (subproject)
│   ├── build.gradle.kts
│   └── src/
├── build-logic/        # Custom build logic (shared configuration)
│   ├── build.gradle.kts
│   └── src/
├── config/             # Gradle configuration files
│   └── gradle-wrapper.properties
├── tests/              # Centralized tests
│   └── README.md
├── docs/               # Project documentation
│   └── README.md
├── settings.gradle.kts # Root Gradle settings using Kotlin DSL
├── build.gradle.kts    # Root build script using Kotlin DSL
└── README.md           # Main project README
```

### Key Directories:
- **app/**: Main application module with Kotlin source code.
- **ui/**: UI-related logic as a subproject.
- **utilities/**: Common utility functions or services.
- **build-logic/**: Contains custom Gradle logic and shared configuration applied across the project. This may include common plugins, tasks, or settings that multiple modules use.
- **config/**: Gradle configuration, including wrapper files.
- **tests/**: Centralized test cases, including integration and shared test utilities.
- **docs/**: Project documentation, including contribution guidelines, API docs, and how-to guides.

## Project Setup

### Prerequisites
- **Java Development Kit (JDK)**: Version 11 or higher.
- **Gradle**: The project uses the Gradle wrapper, so no need to install Gradle globally.

### Cloning the Repository
```bash
git clone https://github.com/your-repo/template-project.git
cd template-project
```

### Initializing the Project
To initialize the project, run the following command to download dependencies:
```bash
./gradlew build
```

## Building the Project

To build the project, including all modules, run:
```bash
./gradlew build
```

For a specific module (e.g., `app`), run:
```bash
./gradlew :app:build
```

## Running Tests

To run all tests for the project:
```bash
./gradlew test
```

To run tests for a specific module:
```bash
./gradlew :utilities:test
```

## Dependency Management

Dependencies for each module are defined in their respective `build.gradle.kts` files.

### Example of Declaring Dependencies:
In `app/build.gradle.kts`:
```gradle
dependencies {
    implementation(project(":utilities"))
    implementation("org.jetbrains.kotlin:kotlin-stdlib")
}
```

## Custom Build Logic

The `build-logic` directory contains shared configuration and custom tasks. This can be used to define custom Gradle plugins, tasks, or shared dependency management that applies to all subprojects.

### Applying Build Logic

In the `settings.gradle.kts`, the `build-logic` is included as part of the project build:

```gradle
pluginManagement {
    includeBuild("build-logic")
}
```

In `build-logic/build.gradle.kts`, you can define shared tasks or settings, for example:
```gradle
plugins {
    `kotlin-dsl`
}

dependencies {
    implementation("org.jetbrains.kotlin:kotlin-gradle-plugin")
}
```

Then, you can apply this shared logic in other subprojects' `build.gradle.kts` files:
```gradle
apply(plugin = "your-custom-plugin")
```

## Continuous Integration

To integrate with a CI service like GitHub Actions, add a workflow configuration file (e.g., `.github/workflows/ci.yml`) that builds and tests the project on every push or pull request:

Example CI pipeline for Gradle:
```yaml
name: CI Pipeline

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up JDK
        uses: actions/setup-java@v2
        with:
          java-version: '11'

      - name: Build with Gradle
        run: ./gradlew build
```

## Contribution Guidelines

If you'd like to contribute, please follow the guidelines in `docs/CONTRIBUTING.md`.

### Steps to Contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
