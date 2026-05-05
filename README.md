<!-- markdownlint-disable MD041 -->
<p align="center">
    <a href="https://github.com/php-forge/baseline" target="_blank">
        <img src="https://avatars.githubusercontent.com/u/103309199?s%25253D400%252526u%25253Dca3561c692f53ed7eb290d3bb226a2828741606f%252526v%25253D4" width="35%" alt="PHP Forge">
    </a>
    <h1 align="center">Baseline</h1>
    <br>
</p>
<!-- markdownlint-enable MD041 -->

<p align="center">
    <strong>Centralized PHP development baseline</strong><br>
    <em>Code style, linters, CI workflows, and dev environment tooling shared across repositories via Composer.</em>
</p>

## System requirements

- [`PHP`](https://www.php.net/downloads) 8.3 or higher.
- [`Composer`](https://getcomposer.org/download/) for dependency management.

## Installation

```bash
composer require php-forge/baseline:^0.1 --dev
```

Or add the dependency manually to `composer.json`:

```json
{
    "require-dev": {
        "php-forge/baseline": "^0.1"
    }
}
```

Then run `composer update`.

## Scaffolded distribution

This package is a [`yii2-extensions/scaffold`](https://github.com/yii2-extensions/scaffold) provider for **dev
environment metadata** (editor, gitignore, prettier, stylelint, super-linter configs, and more). Templates live under
`metadata/` and are mapped to consumer roots via the `{from, to}` form in `scaffold.json`.

Opt in by allowing the plugin and listing this package as an authorised provider:

```bash
composer require yii2-extensions/scaffold:^0.1 --dev
```

```json
{
    "config": {
        "allow-plugins": {
            "yii2-extensions/scaffold": true
        }
    },
    "extra": {
        "scaffold": {
            "auto": false,
            "allowed-packages": ["php-forge/baseline"]
        }
    }
}
```

With `auto: false`, the plugin does not run on `composer install`; sync templates manually:

```bash
vendor/bin/scaffold reapply --provider=php-forge/baseline
vendor/bin/scaffold diff <file>
vendor/bin/scaffold status
```

### Files distributed

```text
.
├── .editorconfig                      # append: Editor settings; consumer-specific lines preserved
├── .gitattributes                     # replace: Text/binary handling, archive excludes
├── .gitignore                         # append: Common ignore patterns; project-specific lines preserved
├── .styleci.yml                       # replace: StyleCI config (PSR-12 + risky)
├── .ecrc                              # replace: editor-config-checker exclusions
├── .prettierignore                    # replace: Paths Prettier should skip
├── .prettierrc.json                   # replace: Prettier formatting rules
├── .stylelintignore                   # replace: Paths stylelint should skip
├── composer-require-checker.json      # preserve: Composer require-checker whitelist (project-specific)
└── .github
    └── linters
        ├── .codespellrc               # replace: codespell config
        ├── .editorconfig-checker.json # replace: editor-config-checker config for Super-Linter
        ├── .gitleaks.toml             # replace: gitleaks config
        ├── .markdown-lint.yml         # replace: markdownlint config
        └── actionlint.yml             # replace: actionlint config for Super-Linter
```

Mode semantics:

- `replace`: lock-step with this package. Local edits trigger a warning and the file is skipped on update.
- `append`: provider content is merged into the existing file; consumer additions never blown away.
- `preserve`: file is written once on first install and never overwritten.

## Related packages

For ECS and Rector configurations and their root wrapper templates, see
[`php-forge/coding-standard`](https://github.com/php-forge/coding-standard). The two packages are independent — adopt
either, both, or neither.

## Package information

[![PHP](https://img.shields.io/badge/%3E%3D8.3-777BB4.svg?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/releases/8.3/en.php)
[![Latest Stable Version](https://img.shields.io/packagist/v/php-forge/baseline.svg?style=for-the-badge&logo=packagist&logoColor=white&label=Stable)](https://packagist.org/packages/php-forge/baseline)
[![Total Downloads](https://img.shields.io/packagist/dt/php-forge/baseline.svg?style=for-the-badge&logo=composer&logoColor=white&label=Downloads)](https://packagist.org/packages/php-forge/baseline)

## Quality code

[![Super-Linter](https://img.shields.io/github/actions/workflow/status/php-forge/baseline/linter.yml?style=for-the-badge&label=Super-Linter&logo=github)](https://github.com/php-forge/baseline/actions/workflows/linter.yml)
[![StyleCI](https://img.shields.io/badge/StyleCI-Passed-44CC11.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.styleci.io/repos/php-forge/baseline?branch=main)

## Our social networks

[![Follow on X](https://img.shields.io/badge/-Follow%20on%20X-1DA1F2.svg?style=for-the-badge&logo=x&logoColor=white&labelColor=000000)](https://x.com/Terabytesoftw)

## License

[![License](https://img.shields.io/badge/License-BSD--3--Clause-brightgreen.svg?style=for-the-badge&logo=opensourceinitiative&logoColor=white&labelColor=555555)](LICENSE)
