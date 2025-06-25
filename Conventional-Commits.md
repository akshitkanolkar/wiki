# Conventional Commits

The [Conventional Commits](https://www.conventionalcommits.org/) specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history, making it easier to build automated tools and maintain a clean, understandable history. This convention dovetails with [Semantic Versioning (SemVer)](https://semver.org/), by describing the features, fixes, and breaking changes made in commit messages.

---

## How should I write my commits?

A Conventional Commit follows this format:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

- **type**: Type of change (required)
- **scope**: Module/package affected (optional, but recommended)
- **description**: Short, imperative summary (required)
- **body**: Detailed explanation (optional)
- **footer**: Breaking changes, issue references (optional)

---

## Common Prefixes

| Type           | Purpose                                  |
|----------------|-------------------------------------------------------------|
| feat(xxx)      | :sparkles: New feature                             |
| fix(xxx)       | :bug: Bug fix                                 |
| docs(xxx)      | :book: Documentation changes                   |
| style          | :gem: Code style (formatting, no logic change) |
| refactor       | :package: Code restructuring, no behavior change  |
| perf(xxx)      | :rocket: Performance improvements                |
| test(xxx)      | :rotating_light: Adding or fixing tests cases                 |
| build(xxx)     | :construction_worker: Build system or dependencies changes |
| ci(xxx)        | :computer: CI/CD pipeline changes                  |
| chore(xxx)     | :ticket: Maintenance tasks                       |
| revert(xxx)    | :back: Reverting commits                       |

**Breaking changes**:  
Use an exclamation mark `!` after the type (e.g., `feat!:`, `fix!:`) to indicate a breaking change that will cause a major version bump according to SemVer.

---

## Examples

### Good Commits

```
git commit -m "feat(lang): add german language support"
```

```
git commit -m "feat(NH-5678): add Home.jsx file"
```

```
git commit -m "fix(auth): resolve login redirect bug"
```

```
git commit -m "build: update offline production app version to v2.1.18 (#46897)"
```

```
git commit -m "refactor(auth): NH-4321 simplify authentication flow"
```

```
git commit -m "chore(deps): update lodash to 4.17.21"
```

---

### Bad Commits

```
git commit -m "Ugly commit"
# ❌ No type, scope, or structured message
```

```
git commit -m "feat Ugly commit version 2"
# ❌ Missing colon, inconsistent message
```

---

## Best Practices

- **Keep your descriptions short but meaningful.**
- **Use scopes whenever possible.**  
  (e.g., `feat(api):`, `fix(ui):`)
- **Reference JIRA or task IDs** in your description or scope if your project requires it.  
  (e.g., `feat(NH-5678): implement user profile page`)
- **Use the body** to explain **what** and **why**, not **how**.
- **Use the footer** for:
  - Breaking changes (start the footer with `BREAKING CHANGE:`)
  - References to JIRA, GitHub issues, etc.

Example with a **body** and **footer**:

```
feat(NH-9876): add user account deactivation

added api endpoint and ui support for deactivating user accounts.
This prevents re-login after deactivation.

BREAKING CHANGE: account status checks are now mandatory in login flow.
```

---

## Why Use Conventional Commits?

- ✅ Automatically generate changelogs.
- ✅ Automatically determine semantic version bumps.
- ✅ Communicate changes clearly across the team and stakeholders.
- ✅ Improve CI/CD automation.
- ✅ Make it easier for others to contribute.

---

## Useful Tools

- [Commitizen](https://www.npmjs.com/package/commitizen) — CLI tool to help write Conventional Commits.
- [Commitlint](https://commitlint.js.org/) — Lint your commit messages to enforce the convention.

---

## References

- [Conventional Commits](https://www.conventionalcommits.org/)
- [VSCode Conventional Commits Extension](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits)
- [Medium Article: Why Conventional Commits?](https://medium.com/neudesic-innovation/conventional-commits-a-better-way-78d6785c2e08)
