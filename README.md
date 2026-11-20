# Git Setup Wizard

**A guided command-line setup for starting a Git repository with confidence.**

[![npm version](https://img.shields.io/npm/v/git-setup-wizard.svg)](https://www.npmjs.com/package/git-setup-wizard)
[![GitHub repository](https://img.shields.io/badge/GitHub-source-blue)](https://github.com/Ashish2106B/git-setup-wizard)

Git Setup Wizard helps developers prepare a new project for Git. It generates a `README.md` and `.gitignore`, lets you review the staged changes, and can create the initial commit after one confirmation.

This repository is a **demo project** documenting a verified run of the published package, version **1.0.1**. It is not the package source repository.

## The problem

Starting a repository often means switching between setup commands, writing starter documentation, choosing ignore rules, and checking what is about to be committed. That can be easy to overlook, especially when sensitive local files are present.

## The solution

Run the wizard from a project directory and follow its CLI flow. It creates starter Git files, presents the staged changes for review, and asks for a single confirmation before creating the initial commit.

## Features

- Generates a `README.md` and `.gitignore` for a project.
- Shows staged changes so they can be reviewed before committing.
- Uses one commit confirmation in the verified workflow.
- Excludes common secret-file patterns, including root and nested `.env`, `secret`, `.pem`, and `.key` files.
- Provides a quick, repeatable setup through `npx` without a global install.

## Technologies

| Technology | Role |
| --- | --- |
| Node.js | Runtime for the CLI package |
| npm / `npx` | Package distribution and execution |
| Git | Staging, reviewing, and committing project files |

## Requirements

- Node.js and npm installed.
- Git installed and available on your `PATH`.
- A project directory where you want to initialize Git setup.

## Installation and usage

The recommended way to run the published package is with `npx`; no global installation is required:

```bash
npx --yes git-setup-wizard@1.0.1
```

Run the command from the project directory you want to set up. Follow the prompts presented by the CLI.

### CLI demonstration

1. Open a terminal in a project directory.

   ```bash
   cd path/to/your-project
   ```

2. Run the published version of Git Setup Wizard.

   ```bash
   npx --yes git-setup-wizard@1.0.1
   ```

3. Follow the wizard's prompts. It generates `README.md` and `.gitignore` as part of the setup.
4. Review the staged changes shown by the wizard. You can also inspect them in the terminal with:

   ```bash
   git status --short
   git diff --cached
   ```

5. When prompted, confirm the initial commit once. The verified workflow completed the initial commit automatically after that single confirmation.
6. Check the repository state:

   ```bash
   git status --short --branch
   git log -1 --oneline
   ```

The commands above show how to launch and inspect a run; they are not a captured transcript. See [Verified results](#verified-results) for the actual recorded outcome.

## Staged review and commit confirmation

Before committing, the wizard presents the staged file changes for review. Check that the generated files and any project files intended for the first commit are appropriate. The tested flow asked for **one commit confirmation**; after confirmation, it created the initial commit automatically. Review carefully before confirming, especially when working in a directory that already contains files.

## Secret-file exclusions

The demo verified exclusion of root-level and nested files matching these patterns:

| Pattern | Examples |
| --- | --- |
| `.env` | `.env`, `config/.env` |
| `secret` | `secret`, `config/secret` |
| `.pem` | `server.pem`, `certs/server.pem` |
| `.key` | `server.key`, `certs/server.key` |

The verification checked the committed tree with `git ls-tree -r --name-only HEAD` and confirmed that none of those files were committed. Safe files `app.txt` and `config/app-config.txt` were committed. Exclusion rules reduce accidental inclusion; always review staged changes before confirming a commit.

## Verified results

The following results were recorded by running the published package, version **1.0.1**:

| Check | Result |
| --- | --- |
| Command | `npx --yes git-setup-wizard@1.0.1` |
| Generated files | `README.md` and `.gitignore` |
| Staged changes | Reviewed before commit |
| Commit confirmation | One confirmation |
| Initial commit | Created automatically; `658443b` |
| Secret-file test | Root and nested `.env`, `secret`, `.pem`, and `.key` files were not committed |
| Safe-file test | `app.txt` and `config/app-config.txt` were committed |
| Tree verification | Used `git ls-tree -r --name-only HEAD` |
| Final state | Working tree clean |

These are the supplied test results for this demo; this repository does not include the package's source code.

## Screenshots

The [`screenshots/`](screenshots/) folder contains a capture guide. Add genuine screenshots from your own terminal run there; no screenshots or terminal output are fabricated in this repository.

## Record a 1–2 minute terminal demo

1. Start a screen recording and show a clean terminal window with the demo project directory visible.
2. Run `npx --yes git-setup-wizard@1.0.1` and capture the actual prompts and generated-file steps.
3. Pause on the staged changes and show how you review them.
4. Show the single commit confirmation and the resulting commit.
5. Briefly show the secret-file exclusion check with `git ls-tree -r --name-only HEAD` (use the test project, and do not display real credentials or private files).
6. End by showing the final commit and clean working tree. Keep the recording between one and two minutes, and use only output from a genuine run.

## Links

- [NPM package](https://www.npmjs.com/package/git-setup-wizard)
- [Main GitHub repository](https://github.com/Ashish2106B/git-setup-wizard)

## License

Refer to the [main package repository](https://github.com/Ashish2106B/git-setup-wizard) for its license. This demo repository does not make a separate license claim.
