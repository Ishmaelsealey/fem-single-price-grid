# Functional Requirements and Notes

## CSS Grid usage

- correct HTML markup
- correct CSS
  - I need to make the grid items 50% on desktop and 100% on mobile
  - `$29 per month` will have to go into a flexbox layout with content justified center
  - no grid gaps needed
  - or 3 grid blocks with the top row grid box starting at column line 1 and ending at column line 2

  ```css
    .item {
        grid-column-start: 1;
        grid-column-end: 2;
        OR
        grid-column: 1 / span 2; // start on column 1 and span 2 columns
      }
  ```

  - use `grid-template-columns: 1fr 1fr; // auto is acceptable in place of 1fr` to share the available space between columns evenly
- how to use CSS grid and 💪📦 (flexbox)
  - for my purpose I would use grid instead of flexbox because  
  flexbox is not at it's best when you give things a defined width.

## Responsive design

- align items differently for different sized screens

## Interactivity

- hover state for sign up CTA => use :hover with the different styling options

## Accessibility

- Correct heading tags
  - use h1 h2 h3 tags and a modified h4 tag or a span tag to style the money
- Screenreader-only text for Section titles
- keeping the grid accessible - [evanto tuts+ article](https://webdesign.tutsplus.com/articles/a-guide-to-css-grid-and-accessibility--cms-32857)

## Restart

I realised that I need to do proper prepwork and spread the  
workload over multiple days or at least not one long coding session.

- Make sure you have the following planned outline
  - Responsive Design - Mobile first Designs
  - Accessibility
  - All functional parts of your website

Style your website to be responsive and accessable from the start.

### Responsive CSS Grid Usage

- Design Mobile first layout. When the screen gets bigger than 700px, then change styles,  
instead of when it gets smaller than 700px
- Use `box-sizing: border-box;`
- Define 12 column classes that give the width of the column

```CSS
.col-1 {width: 8.33%;}
.col-2 {width: 16.66%;}
.col-3 {width: 25%;}
.col-4 {width: 33.33%;}
.col-5 {width: 41.66%;}
.col-6 {width: 50%;}
.col-7 {width: 58.33%;}
.col-8 {width: 66.66%;}
.col-9 {width: 75%;}
.col-10 {width: 83.33%;}
.col-11 {width: 91.66%;}
.col-12 {width: 100%;}
```

- Float all columns left and give a 15px padding

```css
[class*="col-"] {
  float: left;
  padding: 15px;
  border: 1px solid red;
}
```

- Wrap each row in a div and make sure all rows add up to 12 columns.

```html
 <div class="row">
  <div class="col-3">...</div> <!-- 25% -->
  <div class="col-9">...</div> <!-- 75% -->
</div> 
```

The columns inside a row are all floating to the left, and are  therefore taken out of the flow of the page, and other elements  will be placed as if the columns do not exist. To prevent this,  we will add a style that clears the flow:

```css
.row::after {
  content: "";
  clear: both;
  display: table;
}
```

- Next, create a media query that makes the width of each column 100% when the screen width is less than ___ pixels.

```css
@media only screen and (max-width: 768px) {
  [class*="col-"] {
    width: 100%;
  }
}

/* Mobile first design */


@media only screen and (min-width: 768px) {
  .col-1 {width: 8.33%;}
  .col-2 {width: 16.66%;}
  .col-3 {width: 25%;}
  .col-4 {width: 33.33%;}
  .col-5 {width: 41.66%;}
  .col-6 {width: 50%;}
  .col-7 {width: 58.33%;}
  .col-8 {width: 66.66%;}
  .col-9 {width: 75%;}
  .col-10 {width: 83.33%;}
  .col-11 {width: 91.66%;}
  .col-12 {width: 100%;}
}

/* What would be the mobile responsive 
100% width columns would be outside the media query
like the code below*/

[class*="col-"] {
  width: 100%;
}
```

I need to use flexbox to contain the grid box centered on the page.

```html
<div class="flexbox">
  <div class="grid">
    <div class="grid-item"></div>
    <div class="grid-item"></div>
    <div class="grid-item"></div>
  </div>
</div>
```

```css
  .flexbox {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: hsl(204, 43%, 93%);
  }
  /* use a media query to change the background color to hsl(218, 22%, 67%) on desktop */
  /* grid design will follow */
```
