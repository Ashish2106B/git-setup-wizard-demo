# Git Setup Wizard

**An interactive CLI to get a new project ready for Git and GitHub.**

## About

Git Setup Wizard is an npm package that guides you through preparing a project for version control. It brings repository initialization, starter files, an initial commit, and optional GitHub remote setup into one workflow, with a review step before committing.

## Features

- Interactive prompts for the project name, project type, and setup actions.
- Initializes Git for a new repository and sets its initial branch to `main`.
- Generates a starter `README.md` and project-specific `.gitignore` for Node.js, Python, or Java.
- Displays staged filenames and the staged diff for review before a commit.
- Creates an initial commit after confirmation.
- Optionally configures a GitHub URL as `origin` and pushes the current branch after confirmation.
- Excludes common secret-file patterns from automatic staging: `.env*`, `*secret*`, `*.pem`, and `*.key`.

## Requirements

- Node.js 18 or newer
- Git installed and available on your `PATH`
- Git credentials configured locally if you choose GitHub operations

## Try It

Run this from the project directory you want to set up:

```bash
npx --yes git-setup-wizard@1.0.1
```

## How It Works

1. The wizard asks for a project name and type, then offers setup operations.
2. If you choose Git initialization, it creates a repository on `main`. If a `.git` entry already exists, it skips initialization.
3. It can generate a starter README and `.gitignore`; existing files with those names are left unchanged.
4. If you choose the initial commit, it stages eligible files and displays the filenames and diff for review. Confirm to create the commit.
5. GitHub setup is optional. Create an empty GitHub repository first; the wizard can add its URL as `origin` if no `origin` is configured. You can then choose to push the current branch and confirm that action.

Each operation can be declined independently.

## Example Use Case

For a new Node.js project, create its directory and start the wizard:

```bash
mkdir my-app
cd my-app
npx --yes git-setup-wizard@1.0.1
```

Choose **Node.js**, accept the setup actions you want, and review the staged files and diff before confirming an initial commit. To publish it, first create an empty repository on GitHub, then use the optional remote and push steps.

## Safety

- An existing Git repository is not reinitialized.
- Existing `README.md` and `.gitignore` files are preserved.
- Automatic staging excludes `.env*`, `*secret*`, `*.pem`, and `*.key` filenames at the repository root and in nested directories. Sensitive-looking staged filenames also block the commit.
- Review the displayed diff before confirming: filename rules cannot detect secrets stored in ordinary-looking files.
- GitHub remote configuration and pushing are optional and separately confirmed. The wizard uses locally configured Git credentials and does not save them.

## Verification

The published package **1.0.1** was tested with `npx --yes git-setup-wizard@1.0.1`. The recorded run generated `README.md` and `.gitignore`, displayed staged changes for review, and created an initial commit after one confirmation. The demo repository preserves the successful initial commit `658443b` in its history.

A separate secret-file check confirmed that root and nested `.env`, `secret`, `.pem`, and `.key` test files were absent from the committed tree; `app.txt` and `config/app-config.txt` were present.

## Related Links

- [NPM package](https://www.npmjs.com/package/git-setup-wizard)
- [Source code](https://github.com/Ashish2106B/git-setup-wizard)
