# gugus-grid
Minimal grid

This is a bare-bones approach for a css-only forntend grid without the fuss and overhead of current frameworks.

## Customisation
For customisation adjust the following variables:
```
// all classes are generated from this numer

  $baseGrid: 12; 
  
 // the gap between the flexbox elements
 // (the outer gap is reset by negative margins)
 
  $gridPadding: 10px; 
```

## Flebox Grid

### Basic Grid:
The Basic flexbox grid markup

```
<div class="flexGrid">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>

```

### Standardised Sizing
If you want to control the width of the grid elements add classes with a number like so: `col{x}`

```
<div class="flexGrid">
  <div class="col1">Column with full width</div>
  <div class="col4">Column with 1/4 width</div>
  <div class="col">fills the rest of the row</div>
</div>

```

#### Responsive grid
Just add media query based classes to your grid:
```
<div class="flexGrid">
  <div class="col1 colMd4 colLg6">Column with full width. 1/4 on Md size and 1/6 on Lg size</div>
  <div class="col">fills the rest of the row</div>
</div>

```
### Row Columns
You can also define the grid size on the parent element with `flexGrid rowCol{x}`
```
<div class="flexGrid rowCol4">
  <div class="col">1/4 column</div>
  <div class="col">1/4 column</div>
  <div class="col col2">overrides the parent directive/div>
</div>

```
#### Responsive Row Columns
You can also add repsonsive row Columns: ```<div class="flexGrid rowCol4 rowColLg4">```

## Utility first vs. css abstraction
You can also write the whole thing in scss and use your own classes in the html markup:

### Column Row
```
.yourOwnClass {
  @include rowCol(x);
  @include rowColSm(x);
  @include rowColMd(x);
}
```


### Child element
```
.yourOwnClass {
  @include col(x);
  @include colSm(x);
  @include coLg(x);
}
```
## Positioning
There are helper classes if you want to position your stuff:

Naming: `.{orientation}-{css-directive}`

Example: `x-space-between`or `y-center`

Responsive Positioning: `.{orientation}-{breakpoint}-{css-directive}`

Example: `x-md-space-between`or `y-sm-center`

```
<div class="flexGrid rowCol3 x-space-between">
  <div class="col"><p>blabla</p></div>
  <div class="col">blabla blabla blabla blabla blabla blabla blabla blabla</div>
</div>
```
And as always you can also use your own classes like so:

```
.yourOwnClass {
  @include x(space-between);
  @include x-sm(space-evenly);
  @include x-lg(center);
}
```

