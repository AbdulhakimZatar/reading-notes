# Grid Layout
The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

## Grid Elements
A grid layout consists of a parent element, with one or more child elements.

```css
<div class="grid-container">
  <div class="grid-item">1</div>
  <div class="grid-item">2</div>
  <div class="grid-item">3</div>
  <div class="grid-item">4</div>
  <div class="grid-item">5</div>
  <div class="grid-item">6</div>
  <div class="grid-item">7</div>
  <div class="grid-item">8</div>
  <div class="grid-item">9</div>
</div>
```

![example](https://i.ibb.co/jzfHRG2/download.png)


### Display Property
An HTML element becomes a grid container when its display property is set to grid or inline-grid.

```css
.grid-container {
  display: grid;
}

.grid-container {
  display: inline-grid;
}
```

### Grid Columns
The vertical lines of grid items are called columns.

![example](https://www.w3schools.com/css/grid_columns.png)


### Grid Rows
The horizontal lines of grid items are called rows.

![eaxample](https://www.w3schools.com/css/grid_rows.png)


### Grid Gaps
The spaces between each column/row are called gaps.

![eaxmple](https://www.w3schools.com/css/grid_gaps.png)

```css
.grid-container {
  display: grid;
  grid-column-gap: 50px;
}
```