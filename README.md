# Griddle

Griddle is a CSS grid system for modern browsers. It is generated from a set of Sass functions and mixins. The grid uses `inline-block` and `box-sizing` to provide features that float-based layouts cannot.

[Project page](http://necolas.github.com/griddle/)

[Contribution guidelines](https://github.com/necolas/issue-guidelines)

## Features

* Fluid layout.
* Fluid offsets.
* Intelligent cell wrapping.
* Horizontal centering of cells.
* Custom vertical alignment of cells (top, bottom, or middle).
* Cell width is controlled independently of grid gutter.
* Infinite nesting.
* Built-in redundancy coupled with automatic consolidation of rules in compiled CSS.
* Suitable for responsive layouts. Generate styles (tied to HTML classes) to modify cell proportions at different breakpoints.
* RTL support.

## How to use it

The grid system is suitable whether or not you choose to develop "mobile first". Import `grid-helpers` and `grid-core` in order to "initialize" the grid at a given breakpoint.

The `grid-build-units()` mixin handles the generation of styles for grids. It can accept a space-separated list of integers, each of which results in the creation of a grid with that many parts. For example:

```scss
// example-mobile.scss (for min-width >= 30em)
@import "grid-helpers";
@import "grid-core";
// create 2, 3, and 4 column grids
@include grid-build-units(2 3 4);
```

For any subsequent breakpoints specified in separate files, import `grid-helpers` to have access to the `grid-build-units()` mixin. The mixin also accepts a string as a second (optional) argument. This can be used to generate modified selectors to override the width of a cell at different breakpoints. For example:

```scss
// example-desktop.scss (for min-width >= 40em)
@import "grid-helpers";
// create 2, 3, 4, 5, 6, and 12 column grids (wider screens)
@include grid-build-units(2 3 4 5 6 12, '--desktop');
```

You can have a cell that is 50% wide at narrow viewports, but 25% wide at wider viewports when the styles are applied to the modifier class: (`<div class="grid__cell unit-1-2 unit-1-4--desktop>`).

Feel free to customize the default class name pattern to suit your personal preferences.

## Browser support

* Google Chrome
* Firefox
* Safari
* Opera
* Internet Explorer 8+

## License

Public domain
