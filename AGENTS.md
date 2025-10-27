# Repository Guidelines

## Project Structure & Module Organization
- Root files hold reference material: `Apresentação.txt`, `estrutura do site.txt`, and shared assets like `img.png`.
- Prompt briefs live in `prompts/` with the canonical context in `prompt-base.md`.
- Sequenced workflow drafts sit in `prompts/steps/` (01-12). Keep two-digit prefixes to preserve ordering; new steps should start at the next available index (`13-nova-frente.md`).
- Store new imagery in an `img/` directory (create if needed) and reference assets with relative paths inside Markdown files.

## Build, Test, and Development Commands
- `npx markdownlint "**/*.md"` lint Markdown for heading levels, bullet consistency, and spacing issues.
- `npx prettier --check "**/*.{md,txt}"` verify formatting; rerun with `--write` to normalize changed files.
- `npx markdown-link-check prompts/steps/*.md` ensure outbound links stay valid before opening a PR.
- `python -m http.server 8000` (run at repo root) serves a quick local preview when prototyping static HTML variants of the briefs.

## Coding Style & Naming Conventions
- Use ATX headings (`#`, `##`) in sentence case; favor concise paragraphs between 80-100 characters wide.
- Prefer ordered lists for process flows and unordered lists for reference tips; keep bullets parallel and factual.
- Name files in lowercase with hyphens (`sobre-historia.md`); maintain chronological artifacts with two-digit prefixes.
- Name images with descriptive snake_case (`evento_2024.png`); avoid spaces and keep source files in `img/`.

## Testing Guidelines
- Treat lint commands as mandatory gates; resolve every reported warning before requesting review.
- When adding or updating links, run `markdown-link-check` on the affected files and note the results in the PR description.
- Verify new binary assets by opening them locally and documenting the manual check (format, resolution, readability).

## Commit & Pull Request Guidelines
- Follow Conventional Commits (`docs: add eventos brief`), wrapping message bodies at 72 characters.
- Keep each commit focused on a single theme (one prompt revision, one asset upload) to simplify reviews.
- Pull requests should include a goals summary, list of touched files, manual check results, and screenshots or thumbnails for visual updates.
- Reference related tasks with `Closes #id` or external board links, and request reviewers from both content and design stakeholders.
