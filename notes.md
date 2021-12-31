# Functional Requirements and Notes

## CSS Grid usage

- correct HTML markup
- correct CSS
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