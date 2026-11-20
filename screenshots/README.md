# Screenshot capture guide

Capture screenshots from a genuine run of Git Setup Wizard **1.0.1**. Do not create mock terminal output or edit screenshots to imply behavior that did not occur. Before sharing, check every image for usernames, private paths, tokens, credentials, and other sensitive information.

Save approved captures in this folder as PNG files with short, descriptive names. The screenshots are optional; add them only after you have captured and reviewed them.

## Suggested captures

1. **`01-wizard-run.png`** — The terminal showing the actual command used to start the wizard and its setup flow.
2. **`02-staged-review.png`** — The staged changes presented for review, with enough context to identify the generated `README.md` and `.gitignore`.
3. **`03-commit-result.png`** — The one confirmation and the resulting initial commit.
4. **`04-secret-exclusion.png`** — The verification using `git ls-tree -r --name-only HEAD`, showing safe committed files and no test secret files.

## Capture checklist

- Run `npx --yes git-setup-wizard@1.0.1` in a disposable test project.
- Use dummy secret-like filenames and placeholder content only; never create or reveal real secrets for the recording.
- Capture the terminal directly with your operating system's screenshot tool.
- Keep the text readable and include enough terminal context to show which step is being demonstrated.
- Review captures for sensitive values and unrelated personal information before adding them here.
- Use captions in the main README or commit message to explain what each genuine image shows.
