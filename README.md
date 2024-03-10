# PHP Code Quality Tools

CLI tools for running PHP code checks and refactoring for Pimcore

<!-- TOC -->
* [PHP Code Quality Tools](#php-code-quality-tools)
  * [Installation](#installation)
    * [Composer](#composer)
    * [Templates](#templates)
    * [Overwrite rulesets](#overwrite-rulesets)
    * [Disable tools](#disable-tools)
  * [Execute](#execute)
    * [Code checks](#code-checks)
    * [Automatic refactoring](#automatic-refactoring)
  * [Configuring rulesets](#configuring-rulesets)
    * [Configuration](#configuration)
    * [Rulesets](#rulesets)
<!-- TOC -->

## Installation

### Composer
```bash
composer require --dev zieglerh/php-code-quality:^1.0
```

### Templates

Copy `/templates/*` into your project root folder 

### Overwrite rulesets

In your `.env` file you can define a path to overwrite the rulesets, e.g. from your project root

```
PHPCS_RULESET_FILE=./phpcs.xml
PHPMD_RULESET_FILE=./phpmd.xml
```
### Disable tools

You can disable tools in your `.env` file by setting the following

```
PHPCS=0
PHPMD=0
PHPSTAN=0
```

or disable all of them with 
```
CODE_CHECKS_ENABLED=0
```

### Overwrite tool arguments

You can also overwrite tool arguments from `definition_args.conf` in your `.env` file

```
PHPCS_ARGS=...
PHPMD_ARGS=...
PHPSTAN_ARGS=...
```

## Execute

### Code checks

```bash
vendor/bin/code-check
```

To execute only specific tools, you can append one or multiple arguments

```bash
vendor/bin/code-check phpcs phpmd phpstan
```
### Automatic refactoring

Display automatic code refactoring

```bash
vendor/bin/rector process --dry-run
```

Run rector and change all files

```bash
vendor/bin/rector process
```

## Configuring rulesets

### Configuration

For configuration of tools see `defnitions_tools.conf`

### Rulesets

Rulesets are defined inside the rulesets/*.xml files and can be overwritten

See [Overwrite rulesets](#overwrite-rulesets)

