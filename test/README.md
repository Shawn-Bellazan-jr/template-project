# `tests/` Directory

This directory contains all the test cases for the project. The testing framework used in this Kotlin DSL Gradle project may include JUnit, TestNG, or another testing library.

## Structure

- `test/kotlin/`: Unit tests and integration tests written in Kotlin.
- `test/resources/`: Test-related configuration files or mock data.

## Running Tests

To run all tests, use Gradle's test task:

```bash
./gradlew test
```

## Guidelines
- Follow the TDD (Test-Driven Development) approach whenever possible.
- Ensure tests are isolated and independent of external resources.
- Add proper assertions and test all possible edge cases.