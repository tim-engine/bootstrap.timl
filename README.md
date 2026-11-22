<p align="center">
  Bootstrap v5.3 components for Tim Engine
</p>

<p align="center">
  <code>tim install bootstrap</code>
</p>

## Usage

Import everything with one line:

```timl
@import "pkg/bootstrap/bootstrap"

@container():
  @row():
    @col-md-6():
      @alert-success("Saved!")
    @col-md-6():
      @badge-primary("New")
```

Or import a single component file:

```timl
@import "pkg/bootstrap/card"

@card("Hello"):
  @card-text("Body text here.")
```

## Features

Layout and grid:

- `page(title)` full HTML document with Bootstrap CSS and JS from CDN
- Containers (`container`, `container-fluid`, `container-sm` .. `container-xxl`), rows, columns (`col`, `col-1` .. `col-12`, responsive `col-sm-*` .. `col-xxl-*`, auto columns)
- Gutters (`row-g-0` .. `row-g-5`, `row-gx-*`, `row-gy-*`), offsets (`col-offset-*`, `col-offset-md-*` ..), order (`order-0` .. `order-5`, `order-first`, `order-last`)

Content:

- Typography: headings (`h1` .. `h6`), displays (`display-1` .. `display-6`), lead, blockquote, code, lists, muted/small/mark/kbd text, font weights, centered text
- Images and figures: fluid, thumbnail, rounded, circle, figure with caption
- Tables: plain, striped, hover, bordered, borderless, small, dark, contextual (`table-primary` ..), responsive wrapper, head builder from a string array, captions, group dividers

Forms:

- Inputs, labels, textareas, selects, checks, radios, switches, ranges, color and file inputs, floating labels, hidden fields
- Selects take `option` children: `@form-select("country"):` with `@form-option("ro", "Romania")` and `@form-option-selected(...)`
- Input groups: `@input-group():` with `@input-group-text("@")` and `@input(...)`

Components:

- Accordion, alerts (variants plus dismissible), badges (variants plus pills and counters), breadcrumbs, buttons (variants, outlines, sizes, link buttons), button groups and toolbars, cards (headers, footers, images, links), carousel (with captions, fade, id targeting), close buttons, collapse, dropdowns (dropup, dropend, dropstart, center), list groups, modals (sizes, centered, scrollable, fullscreen and responsive fullscreen), navbar, navs and tabs, offcanvas (all placements), pagination (plus auto pages from a total), placeholders, progress bars (variants, striped, animated, stacked), scrollspy, spinners, toasts, tooltips and popovers

Helpers:

- Clearfix, ratios, stretched links, text truncation, vertical rules, visually hidden text, stacks, colored links, `text-bg-*` colors, opacity (`opacity-25` .. `opacity-100`), fixed/sticky positioning, focus rings

## Examples

A page with a navbar, grid and a form:

```timl
@import "pkg/bootstrap/bootstrap"

@page("Sign up"):
  @navbar("Acme"):
    @navbar-nav():
      @nav-item("/home", "Home")
      @nav-item-active("/signup", "Sign up")
  @container():
    @row():
      @col-md-6():
        @card("Create account"):
          @form-control("Email", "email", "email")
          @form-control-floating("Password", "password", "password")
          @form-select("Country"):
            @form-option("ro", "Romania")
            @form-option-selected("us", "United States")
          @form-submit("Sign up")
```

Alerts, badges and progress:

```timl
@alert-success("Profile updated.")
@badge-pill-danger("3")
@progress-bar-striped(65)
```

Modal with a trigger:

```timl
@collapse-toggle("#more", "Details")
@collapse():
  @card-text("Hidden content here.")

@modal("Confirm"):
  p: "Are you sure?"
  @button-danger("Delete")
```

Pagination and tables:

```timl
@table-striped():
  @table-head(["Name", "Email"])
  @tbody():
    @tr():
      @td("Ada")
      @td("ada@example.com")

@pagination-auto(12, 3, "/users")
```

Placeholders while loading:

```timl
@placeholder-glow():
  @placeholder("12")
  @placeholder-primary("8")
```

## Notes

- `@nav-item` and `@nav-item-active` live in `navs.timl`. They work inside `@navbar-nav` too; the aggregator covers both.
- `table-head` takes an array of strings: `@table-head(["A", "B"])`.
- `placeholder` takes a column width as a string: `@placeholder("6")`.
- Select options are child macros (`@form-option`), not arrays.

## Reference

Follows the [Bootstrap 5.3 docs](https://getbootstrap.com/docs/5.3/components/accordion/). Each file links its source page at the top.

### Contributions and Support

- Found a bug? [Create a new Issue](https://github.com/tim-engine/bootstrap.timl/issues)
- Wanna help? [Fork it!](https://github.com/tim-engine/bootstrap.timl/fork)

### License

MIT license. Made by Humans from OpenPeeps.<br>
Copyright &copy; 2023 OpenPeeps & Contributors &mdash; All rights reserved.
