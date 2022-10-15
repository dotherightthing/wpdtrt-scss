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
// -------------------------------------------------------------------
// Imports
// -------------------------------------------------------------------

// Import wpdtrt-scss library helpers
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import _backend styles
@use '../node_modules/wpdtrt-scss/scss/_backend';

// Import theme helpers (optional, can have side-effects on WordPress admin theme)
@use '../scss' as *;

// -------------------------------------------------------------------
// Styles
// -------------------------------------------------------------------
```

#### Frontend (wpdtrt-themename.scss)

```scss
// -------------------------------------------------------------------
// Imports
// -------------------------------------------------------------------

// Import wpdtrt-scss library helpers
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import `include media` library (including default `$breakpoint` map)
@use '../node_modules/include-media/dist/include-media' as *;

// Import _frontend styles (optional)
@use '../node_modules/wpdtrt-scss/scss/_frontend';

// Import theme helpers
@use '../scss' as *;

// Import local icons
@use '../icons/icomoon/style.scss' as *;

// Extend default `$breakpoint` map from library variables
$breakpoints: map-merge($breakpoints, wpdtrt-scss.$breakpoints);

// Extend default `$breakpoint` map from local variables (optional)
$breakpoints: map-merge($breakpoints, $local-breakpoints);

// -------------------------------------------------------------------
// Styles
// -------------------------------------------------------------------
```

#### Frontend (wpdtrt-themename/js/frontend.txt)

Import `:focus-visible` polyfill for older Safari, see [#2](https://github.com/dotherightthing/wpdtrt-scss/issues/2)

```txt
./node_modules/focus-visible/dist/focus-visible.min.js
```

#### Theming (wpdtrt-themename/scss/variables/_css.scss)

```scss
// -------------------------------------------------------------------
// Imports
// -------------------------------------------------------------------

// Import wpdtrt-scss library helpers (optional - mainly for use of `defineColorHSL`)
@use '../../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// -------------------------------------------------------------------
// Variables
// -------------------------------------------------------------------
```

#### Theming (wpdtrt-themename-variables.scss)

```scss
// -------------------------------------------------------------------
// Imports
// -------------------------------------------------------------------

// Import CSS Custom Properties (to bundle backend variables with frontend variables)
@use '../node_modules/wpdtrt-scss/scss/variables/css';

// Import local variables
@use 'variables/css' as *;
```

### Plugin

#### Backend (wpdtrt-pluginname/scss/backend.scss)

Note: `../node_modules/wpdtrt-scss/scss/_backend` is not imported again, as it is assumed that the plugin is being used with a `wpdtrt-themename`, see above.

```scss
// -------------------------------------------------------------------
// Imports
// -------------------------------------------------------------------

// Import wpdtrt-scss library helpers
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import local variables
@use 'variables/scss' as *;

// -------------------------------------------------------------------
// Styles
// -------------------------------------------------------------------
```

#### Frontend (wpdtrt-pluginname/scss/frontend.scss)

Note: `../node_modules/wpdtrt-scss/scss/_frontend` is not imported again, as it is assumed that the plugin is being used with a `wpdtrt-themename`, see above.

```scss
// -------------------------------------------------------------------
// Imports
// -------------------------------------------------------------------

// Import wpdtrt-scss library helpers
@use '../node_modules/wpdtrt-scss/scss' as wpdtrt-scss;

// Import `include media` library (including default `$breakpoint` map)
@use '../node_modules/include-media/dist/include-media' as *;

// Import local variables
@use 'variables/scss' as *;

// Import local icons (optional)
@use '../icons/icomoon/style.scss' as *;

// Import other libraries (optional)

// Extend default `$breakpoint` map from library variables
$breakpoints: map-merge($breakpoints, wpdtrt-scss.$breakpoints);

// Extend default `$breakpoint` map from local variables (optional)
$breakpoints: map-merge($breakpoints, $local-breakpoints);

// -------------------------------------------------------------------
// Styles
// -------------------------------------------------------------------
```

#### Theming (wpdtrt-pluginname-variables.scss)

```scss
// -------------------------------------------------------------------
// Imports
// -------------------------------------------------------------------

// Import local variables
@use 'variables/css' as *;
```

---

### Icons

Icon sets are managed in <https://icomoon.io/app/>.

#### Exporting a set

1. Select *Generate Font*
2. Select the *Download* cog icon
   * Font name: *wpdtrt-pluginname*
   * Class Prefix: *wpdtrt-pluginname-icon-*
   * *Don't* Support IE 8
   * *Don't* Include metadata in fonts
   * *Don't* Embed font is CSS (Premium)
   * *Do* Generate preprocessor variables for: *Sass*
   * *Don't* Generate Dart class for Flutter
   * *Don't* Add empty glyph "0" if missing (for the "ch" unit)
   * CSS Selector: *Use attribute selectors*
   * Font Metrics: *defaults*
   * Metadata: *defaults*
   * Version: *defaults*
3. Unzip and copy contents to *wpdtrt-pluginname/icons/icomoon*
4. Open *wpdtrt-pluginname/icons/icomoon/style.scss*
   * Prepend contents with `/* stylelint-disable */`
5. Open *wpdtrt-pluginname/icons/icomoon/variables.scss*
   * Prepend contents with `/* stylelint-disable */`
   * Replace `$icomoon-font-family: "wpdtrt-pluginname" !default;` with `$icomoon-font-family: "wpdtrt-pluginname";`
   * Replace `$icomoon-font-path: "fonts" !default;` with `$icomoon-font-path: '../icons/icomoon/fonts';`
