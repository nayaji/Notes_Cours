# CSS Cheatsheet: Comprehensive Guide

## 1. **Selectors**
- `*` : Universal selector.
- `#id` : Selects an element by its ID.
- `.class` : Selects elements by class.
- `element` : Selects all elements of that type.
- `element1, element2` : Selects multiple elements.
- `element element` : Descendant selector.
- `element > element` : Direct child selector.
- `element + element` : Adjacent sibling.
- `element ~ element` : General sibling.

### Pseudo-classes
- `:hover` : Applies when the user hovers.
- `:focus` : When an element gains focus.
- `:nth-child(n)` : Selects the nth child.
- `:first-child`, `:last-child` : Selects the first/last child.
- `:not(selector)` : Selects everything except the selector.

### Pseudo-elements
- `::before`, `::after` : Add content before or after an element.

---

## 2. **Box Model**
1. **Content**: The innermost area where text/images appear.
2. **Padding**: Space between content and border.
3. **Border**: Surrounds the padding (or content if no padding).
4. **Margin**: Space outside the border.

### Properties
- `width`, `height`: Content area size.
- `padding`, `margin`: Use `px`, `%`, `em`, `auto`.
- `border`: `border-width` | `border-style` | `border-color`.

---

## 3. **Positioning**
- `static` (default): Normal flow.
- `relative`: Relative to its normal position.
- `absolute`: Relative to the nearest positioned ancestor.
- `fixed`: Relative to the viewport.
- `sticky`: Switches between relative and fixed.

### Offset Properties
- `top`, `right`, `bottom`, `left`.

---

## 4. **Flexbox**
### Parent Properties
- `display: flex` : Activates flexbox.
- `flex-direction`: `row`, `row-reverse`, `column`, `column-reverse`.
- `justify-content`: `flex-start`, `center`, `space-between`, `space-around`.
- `align-items`: `flex-start`, `center`, `stretch`, `baseline`.
- `flex-wrap`: `nowrap`, `wrap`, `wrap-reverse`.

### Child Properties
- `flex-grow`, `flex-shrink`, `flex-basis`.
- `align-self`: Overrides parent `align-items`.

---

## 5. **Grid**
### Parent Properties
- `display: grid`: Activates grid.
- `grid-template-columns`: `repeat()`, `auto-fit`, `auto-fill`.
- `grid-template-rows`.
- `gap`: Space between rows/columns.

### Child Properties
- `grid-column`: Start and end (e.g., `1 / 3`).
- `grid-row`.
- `place-self`: Align individual items.

---

## 6. **Typography**
- `font-family`: `'Arial', sans-serif`.
- `font-size`: `px`, `%`, `em`, `rem`.
- `font-weight`: `normal`, `bold`, `lighter`, `100-900`.
- `line-height`: Controls spacing between lines.
- `text-align`: `left`, `center`, `right`, `justify`.
- `text-decoration`: `none`, `underline`, `line-through`.
- `text-transform`: `capitalize`, `uppercase`, `lowercase`.

---

## 7. **Colors and Backgrounds**
- `color`: Text color.
- `background-color`: Element background color.
- `background-image`: `url('path')`.
- `background-size`: `cover`, `contain`, `auto`.
- `background-repeat`: `repeat`, `no-repeat`.
- `background-position`: `center`, `top`, `left`, etc.

---

## 8. **Transitions and Animations**
### Transitions
- `transition`: `property duration timing-function delay`.
  - Example: `transition: all 0.3s ease-in-out`.

### Animations
- `@keyframes`: Define keyframes.
  ```css
  @keyframes example {
    from {opacity: 0;}
    to {opacity: 1;}
  }
  ```
- `animation`: `name duration timing-function delay iteration-count direction`.

---

## 9. **Media Queries**
- Syntax: `@media (condition) { ... }`.
  - Example:
    ```css
    @media (max-width: 768px) {
      body {
        background-color: lightblue;
      }
    }
    ```

---

## 10. **Common Units**
- `px`: Pixels.
- `%`: Relative to parent.
- `em`: Relative to parent font size.
- `rem`: Relative to root font size.
- `vw`, `vh`: Viewport width/height.
- `fr`: Fractional unit (Grid).

---

## 11. **Z-Index**
- Controls stack order of elements.
- Higher value = On top.
- Only works on positioned elements (`relative`, `absolute`, etc.).

---

## 12. **Clipping and Masking**
- `clip-path`: Define shapes (e.g., circle, polygon).
- `mask`: Apply an image as a mask.

---

## 13. **Utilities and Tricks**
- `overflow`: `hidden`, `scroll`, `auto`.
- `box-shadow`: `h-offset v-offset blur spread color`.
- `text-shadow`: Similar to `box-shadow` but for text.
- `visibility`: `visible`, `hidden`.
- `opacity`: `0` (transparent) to `1` (opaque).

---

### Bonus: Debugging Tips
- Use browser developer tools (Inspect Element).
- Add temporary `outline: 1px solid red` to debug element boundaries.

---

This cheatsheet is designed to provide a quick reference for CSS development, covering essential topics and advanced features. Keep practicing and experimenting to master CSS!

