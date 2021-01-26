# DTRT SCSS

[![GitHub release](https://img.shields.io/github/v/tag/dotherightthing/wpdtrt-scss)](https://github.com/dotherightthing/wpdtrt-scss/releases) [![Build](https://github.com/dotherightthing/wpdtrt-scss/workflows/Build%20and%20release%20if%20tagged/badge.svg?branch=master)](https://github.com/dotherightthing/wpdtrt-scss/actions?query=workflow%3A"Build+and+release+if+tagged") [![GitHub issues](https://img.shields.io/github/issues/dotherightthing/wpdtrt-scss.svg)](https://github.com/dotherightthing/wpdtrt-scss/issues)

SCSS mixins and extends for shared theming across projects.

## Installation

```node
npm install dotherightthing/wpdtrt-scss --save
```

## Update

```node
npm update wpdtrt-scss
```

## Uninstallation

```node
npm uninstall wpdtrt-scss
```

## Usage

### wpdtrt-myproject/scss/wpdtrt-myproject-variables.scss

```scss
// -------------------------------------------------------------------
// Variables
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/variables/css';
@import 'variables/css';
```

### wpdtrt-myproject/scss/backend.scss

```scss
// -------------------------------------------------------------------
// Variables
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/variables/scss';

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

### wpdtrt-myproject/scss/frontend.scss

```scss
// -------------------------------------------------------------------
// Variables
// -------------------------------------------------------------------

@import '../node_modules/wpdtrt-scss/scss/variables/scss';

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

@import '../node_modules/wpdtrt-scss/scss/_frontend';
```
