# Installation guide

## System requirements

- [`PHP`](https://www.php.net/downloads) 8.3 or higher.
- [`Composer`](https://getcomposer.org/download/) for dependency management.

## Installation

### Method 1: Using [Composer](https://getcomposer.org/download/) (recommended)

Install the package as a dev dependency.

```bash
composer require php-forge/baseline:^0.1 --dev
```

### Method 2: Manual installation

Add to your `composer.json`.

```json
{
    "require-dev": {
        "php-forge/baseline": "^0.1"
    }
}
```

Then run.

```bash
composer update
```

## Next steps

- 📖 [Readme](../README.md)
