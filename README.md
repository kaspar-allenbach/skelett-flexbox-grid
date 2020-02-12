# do not use! under heavy development

# skelett flexbox grid
Minimal grid

This is a flexbox toolset library
It is meant to be a barebones (German: Skelett) flexbox framework without any styling to not interfere with the rest of your project.

The idea is also that you can use it to save aging websites by just drop in this library and minimise css injections.


## Flebox Grid
By default the grid is a `$baseGrid: 12;` 12 column grid.

## Install
*NPM* `npm i skelett-flexbox-grid -s`

# How To

## Basic Grid:
That's the basic flexbox grid markup
Then just add utility classes as you need them (See Table)

```
<div class="o-flex"> // initiate the flexbox parent element
  <div class="o-col"></div> // initiate the flexbox child element
  <div class="o-col"></div>
  <div class="o-col"></div>
</div>

```


## Standardised Sizing
If you want to control the width of the grid elements add classes with a number like so: `o-col-{x}`

```
<div class="o-flex">
  <div class="o-col-12">Column with full width</div>
  <div class="o-col-4">Column with 1/4 width</div>
  <div class="o-col">fills the rest of the row</div>
</div>

```

## Responsive grid
Just add media query based classes to your grid
This library juses the [skelett-media-query](https://github.com/kaspar-allenbach/skelett-media-queries) library.
All classes are avalable with the media query string `xx_up xx_down`

```
<div class="o-flex">
  <div class="o-col-1 o-col-sm_up-4 o-col-md_up-2">Column with full width. 1/4 on Md size and 1/6 on Lg size</div>
  <div class="col">fills the rest of the row</div>
</div>

```
### Row Columns
You can also define the grid size on the parent element with `o-flex u-row-col-{x}`
```
<div class="o-flex u-row-col-4">
  <div class="o-col">1/4 column</div>
  <div class="o-col">1/4 column</div>
  <div class="o-col col2">overrides the parent directive/div>
</div>

```

## Extends
In case you don't want/can't change the html maruk everything is avalabe as extends as well:

```
.yourOwnClass {
  @extend %o-flex;
  @include %u-row-sm_up-4;
  @include %u-row-lg_up-2;
}
```

# Helpers
There are helper classes for all the stuff

- *Direction* `u-direction-{css-directive}` eg. `u-direction-column-reverse`
- *Gap* `Not implemented yet. I'm just no happy with the negative margin solution which is used everywhere`
- *Order* `u-col-order-{X} eg. `u-col-order-sm__up-4`
- *Positioning* `u-x-{X}` `u-i-{Y}` eg. `u-x-space-between`. X & Y refer to the standard axis.
- *Sizing* `u-shrink-true`, `u-shrink-false`


# Avalable Classes

| non-responsive class  | XL | LG | MD | SM | XS |
| --------------------- | --- | --- | --- | --- | --- |
| `.o-flex`  | `.o-flex-xl__up` `-o-flex-xl__down`  | `.o-flex-lg__up` `-o-flex-lg__down` | `.o-flex-md__up` `-o-flex-md__down` |

