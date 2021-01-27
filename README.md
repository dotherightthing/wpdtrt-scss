# DTRT SCSS

[![GitHub release](https://img.shields.io/github/v/tag/dotherightthing/wpdtrt-scss)](https://github.com/dotherightthing/wpdtrt-scss/releases) [![Build](https://github.com/dotherightthing/wpdtrt-scss/workflows/Build%20and%20release%20if%20tagged/badge.svg?branch=master)](https://github.com/dotherightthing/wpdtrt-scss/actions?query=workflow%3A"Build+and+release+if+tagged") [![GitHub issues](https://img.shields.io/github/issues/dotherightthing/wpdtrt-scss.svg)](https://github.com/dotherightthing/wpdtrt-scss/issues)

SCSS mixins and extends for shared theming across projects.

## Installation

```node
npm install github:dotherightthing/wpdtrt-scss#semver:* --save
```

## Update

```node
npm install github:dotherightthing/wpdtrt-scss#semver:* --save
```

## Uninstallation

```node
npm uninstall wpdtrt-scss
```

## Usage

### wpdtrt-themename/scss/wpdtrt-themename-backend.scss

1. Import `$breakpoint` map (for use with `@include media`)
1. Import theme variables
1. Import `@mixin` helpers (for optional use)
1. Import `@extend` helpers (for optional use)
1. Import backend styling (for use by any plugin built with `generator-wpdtrt-plugin-boilerplate`)
1. Add any theme styling as required

```scss
// -------------------------------------------------------------------
// Variables
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/variables/scss';
@import 'variables/scss';

// -------------------------------------------------------------------
// Mixins
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/mixins';

// -------------------------------------------------------------------
// Extends
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/extends';

// -------------------------------------------------------------------
// Styles
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/_backend';
```

### wpdtrt-pluginname/scss/backend.scss

1. Import `$breakpoint` map (for use with `@include media`)
1. Import theme variables
1. Import `@mixin` helpers (for optional use)
1. Import `@extend` helpers (for optional use)
1. Add any plugin styling as required

```scss
// -------------------------------------------------------------------
// Variables
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/variables/scss';
@import 'variables/scss';

// -------------------------------------------------------------------
// Mixins
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/mixins';

// -------------------------------------------------------------------
// Extends
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/extends';

// -------------------------------------------------------------------
// Styles (Optional)
// -------------------------------------------------------------------

```

### wpdtrt-themename/scss/wpdtrt-themename.scss / wpdtrt-pluginname/scss/frontend.scss

1. Import `$breakpoint` map (for use with `@include media`)
1. Import theme or plugin variables
1. Import `@mixin` helpers (for optional use)
1. Import `@extend` helpers (for optional use)
1. Optionally import frontend styles (which apply extends to common elements)

```scss
// -------------------------------------------------------------------
// Variables
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/variables/scss';
@import 'variables/scss';

// -------------------------------------------------------------------
// Mixins
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/mixins';

// -------------------------------------------------------------------
// Extends
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/extends';

// -------------------------------------------------------------------
// Styles (Optional)
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/_frontend';
```

### wpdtrt-themename/scss/wpdtrt-themename-variables.scss

1. Optionally import `@mixin` helpers (for use of `defineColorHSL` in `wpdtrt-themename/scss/variables/css`)
2. Import CSS Custom Properties (to bundle backend variables with frontend variables)
3. Import theme frontend variables

```scss
// -------------------------------------------------------------------
// Mixins
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/mixins';

// -------------------------------------------------------------------
// Variables
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/variables/css';
@import 'variables/css';
```
