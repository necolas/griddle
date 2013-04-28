# Griddle

Griddle is a CSS grid system for modern browsers. It is generated from a set of
Sass functions and mixins. The grid uses `inline-block` and `box-sizing` to
provide features that float-based layouts cannot.

[Project page](http://necolas.github.com/griddle/)

[Contribution guidelines](https://github.com/necolas/issue-guidelines)

## Installation

* Download: [zip](https://github.com/necolas/griddle/zipball/master)
* [Bower](http://bower.io/): `bower install --save griddle`
* Git: `git clone https://github.com/necolas/griddle.git`

## Features

* Fluid layout.
* Intelligent cell wrapping.
* Horizontal centering of cells.
* Custom vertical alignment of cells (top, bottom, or middle).
* Cell width is controlled independently of grid gutter.
* Infinite nesting.
* Built-in redundancy coupled with automatic consolidation of rules in compiled
  CSS.
* Modify the grid at different breakpoints for responsive layouts.
* RTL support.

## How to use it

The grid system is suitable whether or not you choose to develop "mobile
first". Import `griddle` to "initialize" the grid at a given breakpoint.

The `griddle-build()` mixin handles the generation of styles for grids. It can
accept a space-separated list of integers, each of which results in the
creation of a grid with that many parts. For example:

```scss
@import "griddle";
// Create 2, 3, and 4 column grids
@include griddle-build(2 3 4);
```

The mixin also accepts a string as a second (optional) argument. This can be
used to generate modified selectors to override the width of a cell at
different breakpoints. For example:

```scss
@media (min-width: 40em) {
    // Create 2, 3, 4, 5, 6, and 12 column grids (wider screens)
    @include griddle-build(2 3 4 5 6 12, '--desktop');
}
```

Each grid cell is created in the same way, using HTML classes. You can have a
cell that is 50% wide at narrow viewports, but 25% wide at wider viewports when
the styles are applied to the modifier class:

```html
<div class="grid__cell unit-1-2 unit-1-4--desktop">
    ...
</div>
```

Feel free to customize the default class name pattern to suit your personal
preferences.

## Browser support

* Google Chrome
* Firefox
* Safari
* Opera
* Internet Explorer 8+

## License

MIT License
