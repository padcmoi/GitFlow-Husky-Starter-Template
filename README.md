# 🚀 GitFlow Husky Starter Template

A pro template to kickstart your JS/TS project with:

- Automated GitFlow (releases, hotfixes, versioning, tags)
- Husky (advanced hooks, Git protections, commitlint)
- Automatic changelog
- ESLint, Prettier, ready-to-use VSCode config

## ⚡ Quick Installation

```bash
git clone https://github.com/padcmoi/GitFlow-Husky-Starter-Template my-project
cd my-project
pnpm install
pnpm exec husky install
```

## 🧭 GitFlow Commands

```bash
RELEASE:
  ./gitflow release start <X.Y.0>    # Start a release (PATCH = 0)
  ./gitflow release auto             # Auto: MAJOR.(MINOR+1).0
  ./gitflow release finish           # Merge->main, tag, FF->develop
  ./gitflow release delete           # Delete current release branch
  ./gitflow release rebase           # Rebase release onto develop
  ./gitflow release compare          # Compare release/* with main & develop

  Notes: Strict SemVer versions X.Y.Z

HOTFIX:
  ./gitflow hotfix start <X.Y.Z>     # Start a hotfix (PATCH > 0)
  ./gitflow hotfix auto              # Auto: MAJOR.MINOR.(PATCH+1)
  ./gitflow hotfix finish            # Merge->main, tag, FF->develop
  ./gitflow hotfix delete            # Delete current hotfix branch
  ./gitflow hotfix rebase            # Rebase hotfix onto main
  ./gitflow hotfix compare           # Compare hotfix/* with main

  Notes: Strict SemVer versions X.Y.Z

FEATURE:
  ./gitflow feature start <name>     # Start a feature branch
  ./gitflow feature finish           # Merge feature/* into develop
  ./gitflow feature delete           # Delete current feature branch
  ./gitflow feature rebase           # Rebase feature onto develop
  ./gitflow feature compare          # Compare feature/* with develop

  Notes: Branch names are automatically cleaned

BUGFIX:
  ./gitflow bugfix start <name>      # Start a bugfix branch
  ./gitflow bugfix finish            # Merge bugfix/* into develop
  ./gitflow bugfix delete            # Delete current bugfix branch
  ./gitflow bugfix rebase            # Rebase bugfix onto develop
  ./gitflow bugfix compare           # Compare bugfix/* with develop

  Notes: Branch names are automatically cleaned

DEVELOP:
  ./gitflow develop                  # Interactive develop menu
  ./gitflow develop merge-main       # Merge origin/main → develop
  ./gitflow develop restore          # Recreate develop from main
  ./gitflow develop compare          # Compare develop with main

  Notes: develop is protected and must never diverge

General:
  - 'help' or '?' at any position shows this help
  - Versions must strictly follow SemVer X.Y.Z
  - Feature/bugfix branch names are automatically cleaned
```

## 🦾 Protections & Conventions

- `main` and `develop` branches: direct commits are forbidden, only merges via GitFlow are allowed.
- Commitlint: allowed commit types are: `fix`, `feat`, `docs`, `style`, `refactor`, `perf`, `test`, `chore`, `build`, `ci`, `revert`, `remove`.
  - Recommended scopes: `api1`, `api2`, `db`, `ui`, `core`.
  - Subject required, max 100 characters.
- Husky hooks: strict control of commit messages, branch protection, automatic checks (lint, format, etc.).

## 📝 Changelog & Tools

- Changelog generated automatically: includes version, date, and changes (feat, fix, etc.) from commits.
- ESLint: `pnpm code:lint` / `pnpm code:lint-fix`
- Prettier via `.prettierrc`
- VSCode config in `.vscode/`

## 📂 Structure

```
.husky/ (libs, meta, logs)
.vscode/
CHANGELOG.md
package.json
gitflow
...
```

## 📦 Prerequisites

- Node.js ≥ 22, pnpm, Git ≥ 2.30

## 📜 License

MIT
