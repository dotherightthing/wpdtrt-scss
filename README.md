# DTRT SCSS

[![GitHub release](https://img.shields.io/github/v/tag/dotherightthing/wpdtrt-scss)](https://github.com/dotherightthing/wpdtrt-scss/releases) [![Build](https://github.com/dotherightthing/wpdtrt-scss/workflows/Build%20and%20release%20if%20tagged/badge.svg?branch=master)](https://github.com/dotherightthing/wpdtrt-scss/actions?query=workflow%3A"Build+and+release+if+tagged") [![GitHub issues](https://img.shields.io/github/issues/dotherightthing/wpdtrt-scss.svg)](https://github.com/dotherightthing/wpdtrt-scss/issues)

SCSS mixins and extends for shared theming across projects.

Note: DTRT SCSS uses the [DTRT NPM Scripts](https://github.com/dotherightthing/wpdtrt-npm-scripts) build system. Please ensure that is up to date.

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

### Theme

#### Backend (wpdtrt-themename-backend.scss)()

```scss
// Import wpdtrt-scss library helpers
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import _backend styles
@use '../node_modules/wpdtrt-scss/scss/_backend';

// Import local variables
@use 'variables/scss' as *;

// Add theme styling (as required)
```

#### Frontend (wpdtrt-themename.scss)

```scss
// Import wpdtrt-scss library helpers
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import `include media` library (including default `$breakpoint` map)
@use '../node_modules/include-media/dist/include-media' as *;

// Import _frontend styles (optional)
@use '../node_modules/wpdtrt-scss/scss/_frontend';

// Import local variables
@use 'variables/scss' as *;

// Extend default `$breakpoint` map from library variables
$breakpoints: map-merge($breakpoints, wpdtrt-scss.$breakpoints);

// Extend default `$breakpoint` map from local variables (optional)
$breakpoints: map-merge($breakpoints, $local-breakpoints);

// Add theme styling (as required)
```

#### Frontend (wpdtrt-themename/js/frontend.txt)

Import `:focus-visible` polyfill for older Safari, see [#2](https://github.com/dotherightthing/wpdtrt-scss/issues/2)

```txt
./node_modules/focus-visible/dist/focus-visible.min.js
```

#### Theming (wpdtrt-themename-variables.scss)

```scss
// Import wpdtrt-scss library helpers (optional - mainly for use of `defineColorHSL` mixins)
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import CSS Custom Properties (to bundle backend variables with frontend variables)
@use '../node_modules/wpdtrt-scss/scss/variables/css';

// Import local variables
@import 'variables/css' as *;
```

### Plugin

#### Backend (wpdtrt-pluginname/scss/backend.scss)

```scss
// Import wpdtrt-scss library helpers
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import _backend styles
@use '../node_modules/wpdtrt-scss/scss/_backend';

// Import local variables
@use 'variables/scss' as *;

// Add theme styling (as required)
```

#### Frontend (wpdtrt-pluginname/scss/frontend.scss)

```scss
// Import wpdtrt-scss library helpers
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import `include media` library (including default `$breakpoint` map)
@use '../node_modules/include-media/dist/include-media' as *;

// Import local variables
@use 'variables/scss' as *;

// Extend default `$breakpoint` map from library variables
$breakpoints: map-merge($breakpoints, wpdtrt-scss.$breakpoints);

// Extend default `$breakpoint` map from local variables (optional)
$breakpoints: map-merge($breakpoints, $local-breakpoints);

// Add theme styling (as required)
```

#### Theming (wpdtrt-pluginname-variables.scss)

```scss
// Import local variables
@import 'variables/css' as *;
```
