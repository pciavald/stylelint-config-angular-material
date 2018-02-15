# stylelint-config-angular-material

Shareable stylelint config for Angular Material.

## Installation

```bash
npm install --save-dev stylelint-config-angular-material
```

## Usage

Extend this config within your [stylelint configuration object](http://stylelint.io/user-guide/configuration/#extends),
and add your [rules](https://stylelint.io/user-guide/rules) if needed.

### Example usage with JSON config:

```json
{
  "extends": "stylelint-config-angular-material",
  "ignoreFiles": [
    "node_modules/**/*",
    "dist/**/*"
  ],
  "rules": {
    "string-quotes": "single"
  }
}
```

### Example usage with YAML config:

```yaml
extends: stylelint-config-angular-material
ignoreFiles:
  - node_modules/**/*
  - dist/**/*
rules:
  string-quotes: single
```

### Using custom BEM prefix

Below are example rules for using custom component prefix. Replace "mk" with your own abbreviation.

#### In JSON config:

```json
{
  "rules": {
    "custom-media-pattern": "^mat?-.+",
    "custom-property-pattern": "^mat?-.+",
    "selector-class-pattern": ["^mat?-.+", {
      "resolveNestedSelectors": true
    }],
    "selector-id-pattern": "^mat?-.+",
    "plugin/selector-bem-pattern": {
      "componentSelectors": "^\\.mat?-{componentName}(?:__[a-z]+(?:-[a-z]+)*)*(?:--[a-z]+(?:-[a-z]+)*)*(?:\\[.+\\])*$"
    },
    "scss/dollar-variable-pattern": ["^_?mat-.+", {
      "ignore": "local"
    }],
    "scss/at-function-pattern": "^mat-.+",
    "scss/at-mixin-pattern": "^mat-.+"
  }
}
```

#### In YAML config:

```yaml
rules:
  custom-media-pattern: ^mat?-.+
  custom-property-pattern: ^mat?-.+
  selector-class-pattern:
    - ^mat?-.+
    - resolveNestedSelectors: true
  selector-id-pattern: ^mat?-.+
  plugin/selector-bem-pattern:
    componentSelectors: ^\.mat?-{componentName}(?:__[a-z]+(?:-[a-z]+)*)*(?:--[a-z]+(?:-[a-z]+)*)*(?:\[.+\])*$
  scss/dollar-variable-pattern:
    - ^_?mat-.+
    - ignore: local
  scss/at-function-pattern: ^mat-.+
  scss/at-mixin-pattern: ^mat-.+
```
