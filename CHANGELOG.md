# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## 0.1.8 Under development

## 0.1.7 July 08, 2026

- ci: update codespell skip list to remove redundant entry for metadata directory.

## 0.1.6 July 08, 2026

- ci: update codespell skip list to remove duplicate entry.

## 0.1.5 July 05, 2026

- ci: update codespell skip list to include `CHANGELOG.md` and `UPGRADE.md`.

## 0.1.4 July 05, 2026

- ci: exclude VSCode and local GitHub CLI and Copilot config paths from scaffolded quality checks.

## 0.1.3 July 04, 2026

- ci: replace Super-Linter with reusable quality and security workflows, group Dependabot updates, and refresh scaffolded linter and Gitleaks configs.

## 0.1.2 May 19, 2026

- fix: remove `phpunit.xml` from `.gitignore` and update `composer-require-checker.json` structure.

## 0.1.1 May 06, 2026

- fix: enable `[extend] useDefault = true` in `.github/linters/.gitleaks.toml` so consumers load gitleaks default rules instead of disabling the secret scan.

## 0.1.0 May 05, 2026

- feat: initial release as `yii2-extensions/scaffold` provider for dev environment standards (editor, linters, CI).
- feat: allow shipping of metadata files in dist archive by overriding export-ignore rules.
- feat: add `gitattributes` for metadata files and update `scaffold.json` references.
- feat: update `.ecrc` and `.prettierignore` to include `scaffold-lock.json` for better file management.
- feat: add `.editorconfig-checker.json` for improved linting configuration.
- feat: add `.editorconfig-checker.json` in scaffold for baseline configuration.
- fix: remove obsolete `.ecrc` file from metadata directory.
- fix: update `.codespellrc` to exclude additional files from spell checking.
