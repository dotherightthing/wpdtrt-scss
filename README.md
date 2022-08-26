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

### wpdtrt-themename-backend.scss / wpdtrt-themename.scss / wpdtrt-pluginname/scss/backend.scss / wpdtrt-pluginname/scss/frontend.scss

```scss
// Import wpdtrt-scss library helpers (prefixed with `wpdtrt-scss-`)
@use '../node_modules/wpdtrt-scss/scss';

// Import `include media` library (including default `$breakpoint` map)
@use '../node_modules/include-media/dist/include-media' as *;

// Import _backend styles (if backend stylesheet, optional)
@use '../node_modules/wpdtrt-scss/scss/_backend';

// Import _frontend styles (if frontend stylesheet - but only in theme to prevent conflicts, optional)
@use '../node_modules/wpdtrt-scss/scss/_frontend';

// Import local variables
@use 'variables/scss' as *;

// Extend default `$breakpoint` map from library variables
$breakpoints: map-merge($breakpoints, $wpdtrt-scss-breakpoints);

// Extend default `$breakpoint` map from local variables (optional)
$breakpoints: map-merge($breakpoints, $local-breakpoints);

// Add theme styling (as required)
```

### wpdtrt-themename-variables.scss

1. Optionally import `@mixin` helpers (for use of `defineColorHSL` in `wpdtrt-themename/scss/variables/css`)
2. Import CSS Custom Properties (to bundle backend variables with frontend variables)
3. Import theme frontend variables

```scss
// Import wpdtrt-scss library helpers (prefixed with `wpdtrt-scss-`, optional - mainly for use of `defineColorHSL`)
@use '../node_modules/wpdtrt-scss/scss';

// Import CSS Custom Properties (to bundle backend variables with frontend variables)
@use '../node_modules/wpdtrt-scss/scss/variables/css';

// Import local variables
@import 'variables/css' as *;
```

### wpdtrt-themename/js/frontend.txt

1. Import `:focus-visible` polyfill for older Safari, see [#2](https://github.com/dotherightthing/wpdtrt-scss/issues/2)

```txt
./node_modules/focus-visible/dist/focus-visible.min.js
```
