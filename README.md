# Kotlin DSL Gradle Project Template

A template for projects using Kotlin DSL with Gradle.

## Directory Structure

- [`src/`](src/README.md): Contains the Kotlin source code and resources.
- [`tests/`](tests/README.md): Contains unit and integration test cases.
- [`config/`](config/README.md): Gradle configuration files and build scripts.
- [`docs/`](docs/README.md): Project documentation such as API references and contribution guidelines.

## Getting Started

### Prerequisites

- **JDK**: Java Development Kit (JDK) 11 or higher.
- **Gradle**: This project uses the Gradle wrapper, so no need for a local Gradle installation.

### Build the Project

To build the project, run:

```bash
./gradlew build
```
`
### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/username/repository.git
    ```
   
2. Install the dependencies:
    ```bash
    npm install
    ```

3. Start the development server:
    ```bash
    npm start
    ```

## Branching Strategy

This repository follows the **GitFlow** branching model:

- **main**: Stable production code.
- **develop**: Integration of features before merging to main.
- **feature/xxx**: New features or bug fixes, created from develop and merged back after completion.
- **release/xxx**: Release preparation branches.
- **hotfix/xxx**: Quick fixes to the main branch.

### Example Flow:

1. Create a feature branch from `develop`:
   ```bash
   git checkout -b feature/feature-name
   ```

2. After completing work, push the feature and create a pull request to merge back into `develop`.

## Commit Message Guidelines

Follow [Conventional Commits](https://www.conventionalcommits.org/) for consistency:

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation changes
- `style`: Code style changes (white-space, formatting, etc.)
- `refactor`: Code changes that neither fix a bug nor add a feature
- `test`: Adding or modifying tests
- `chore`: Changes to the build process or auxiliary tools

**Example:**

```bash
git commit -m "feat(auth): add user login functionality"
```

## Contributing

We welcome contributions! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) file for details on our code of conduct and submission guidelines.

1. Fork the repository.
2. Create your feature branch: `git checkout -b feature/feature-name`.
3. Commit your changes: `git commit -m 'Add some feature'`.
4. Push to the branch: `git push origin feature/feature-name`.
5. Submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
