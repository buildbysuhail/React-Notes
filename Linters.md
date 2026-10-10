# Linters — ESLint and Oxlint

## 1. What is a linter?

A **linter** is a development tool that analyzes source code to identify potential mistakes, suspicious patterns, and violations of configured rules.

It checks code without needing to run the application.

Example:

```js
const lectureTitle = "React Basics";

console.log(lectureTtle);
```

The variable `lectureTtle` is misspelled. A suitable linter rule can report that it is undefined.

Other examples of linting checks:

* Unused variables and imports.
* Undefined variables.
* Incorrect React Hook dependency arrays.
* Suspicious or potentially unsafe code patterns.
* Violations of a team's coding rules.

**Purpose:** Find issues early, improve consistency, and make code easier to maintain.

---

## 2. ESLint

**Definition:** ESLint is an established, extensible linter for JavaScript and TypeScript projects.

### Main purposes

* Detect common programming mistakes.
* Enforce configurable code-quality rules.
* Support React and React Hooks through plugins.
* Support custom rules and project-specific conventions.
* Integrate with code editors, CI pipelines, and GitHub Actions.

### Use cases

* React applications with many components and Hooks.
* Projects requiring custom linting rules.
* Teams with established JavaScript standards.
* Applications that depend on specialized plugins, such as accessibility checks.

### Example

ESLint can warn when a React Hook is called incorrectly or when a variable is declared but never used, depending on the configured rules.

---

## 3. Oxlint

**Definition:** Oxlint is a high-performance JavaScript and TypeScript linter from the Oxc toolchain.

### Main purposes

* Analyze code very quickly.
* Detect many common errors and suspicious patterns.
* Provide useful linting for JavaScript and TypeScript projects.
* Reduce linting time in large codebases.

### Use cases

* Large repositories where linting speed matters.
* Projects whose required checks are covered by Oxlint's available rules.
* Teams that want fast feedback during development or automated checks.

### Important limitation

Oxlint's rule and plugin ecosystem differs from ESLint's. Don't assume every ESLint plugin or custom rule can be replaced directly with Oxlint.

---

## 4. ESLint vs Oxlint

| Feature            | ESLint                                         | Oxlint                                                 |
| ------------------ | ---------------------------------------------- | ------------------------------------------------------ |
| Main strength      | Extensibility and ecosystem                    | High speed                                             |
| React support      | Mature plugin ecosystem                        | Supports many relevant rules; verify specific coverage |
| Custom rules       | Extensive flexibility                          | Different and evolving capabilities                    |
| Best fit           | Projects needing detailed, configurable checks | Projects prioritizing speed and covered rules          |
| Learning resources | Extensive                                      | Comparatively smaller ecosystem                        |

---

## 5. How does linting work?

1. Write JavaScript or React code.
2. Run the linter or let your editor run it automatically.
3. Review the reported errors and warnings.
4. Fix the issues or deliberately adjust the rules where appropriate.
5. Run tests and build the application.

A linter may also offer automatic fixes for supported rules.

Example command:

```bash
npx eslint src
```

The exact command depends on the tool and project configuration.

---

## 6. Linter vs Formatter vs Tester

### Linter — ESLint / Oxlint

Checks whether code follows rules and flags suspicious patterns.

### Formatter — Prettier

Automatically formats code, including indentation, spacing, and line breaks.

### Tester — Vitest / React Testing Library

Checks whether code or application behavior works as expected.

These tools complement each other; none completely replaces the others.

---

## 7. Which should I choose?

**For a new React project:** Start with ESLint and the React Hooks rules if you want a mature ecosystem and flexible checks.

Choose Oxlint when speed is a priority and its supported rules cover your needs. Some projects use both, with care to avoid redundant checks.

For your Luminar Lectures project, a simple setup is enough:

* Vite — development server and production build.
* ESLint — code-quality checks.
* Prettier — optional consistent formatting.
* React Testing Library and Vitest — optional tests as the application grows.

**Remember:** A linter helps you find potential problems; it does not guarantee bug-free code or replace testing.
