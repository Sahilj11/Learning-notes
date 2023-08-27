## Selectors 
- Use `*` to apply css to everything on a document
- use , to apply css to multiple elements 
- Use element (space) element , to apply css to child of parent element
```
`*` {
  font-family: monospace;
}

h1 , h2 {
 color: black;
}

p span {
  color: purple;
}
```
- here last property gets applied if on same element different css is been applied 
- but above rule is override when there is specificity
- 
## Colors
- to apply color you can also use `rgb(255,0,0)` this will result in red
- also `rgba(0,0,0,1)` here it is used to define transparency , last arguments is used to set scale of transparency
- ![[Pasted image 20230619102922.png]]
- by clicking on color box
- ![[Pasted image 20230619103218.png]]
- you can toggle color option by click top bar . here hsla, In CSS (Cascading Style Sheets), HSLA refers to the HSL with Alpha color model. It is a way to define colors using the Hue, Saturation, Lightness, and Alpha (transparency) values.
- use coolors.co to pick coolor palatte
- use contrast checker on above site . check the rating of color to ensure more readibility 

## Units and sizes
- ![[Pasted image 20230619110017.png]]
- default size of font in browser is 16px 
- but to ensure that font size remain same use 16px in html tag (suppose user change font size from browser settings)
- you can use width: % , to change the size of element from what it was alloted
- using % is relative to the parent element . 
	- ![[Pasted image 20230619110952.png]]
	- above h1 have 50% of the availabe 100% from header . if we change header width to 80% . h1 will have 50% of 80%  
- In CSS, both `rem` and `em` are units used to specify sizes. Here's an explanation of each:
	1. `rem` (root em): This unit is relative to the root element's font size. By default, the root element is the `<html>` element. When you specify a size in `rem`, it will be calculated based on the root element's font size. If you change the font size of the root element, all elements using `rem` units will adjust accordingly.
	2. `em` (em): This unit is relative to the font size of the current element or the parent element, depending on where it is used. If you specify a size in `em` within an element, it will be calculated based on the font size of its parent element. If no parent element has a defined font size, it will be calculated based on the browser's default font size, typically 16 pixels.
- Here's an example to illustrate the difference between `rem` and `em`
``` css
html {
  font-size: 16px; /* Root font size */
}
body {
  font-size: 1.2rem; /* 1.2 times the root font size (19.2px) */
}
h1 {
  font-size: 2em; /* 2 times the font size of the parent element (38.4px) */
}
p {
  font-size: 1.5em; /* 1.5 times the font size of the parent element (28.8px) */
}
```
- In the example above, the `body` element has a font size of `1.2rem`, which is calculated based on the root font size of `16px`. The `h1` element within `body` has a font size of `2em`, which means it will be twice the font size of its parent (`body`), resulting in `38.4px`. Similarly, the `p` element has a font size of `1.5em`, making it 1.5 times the font size of its parent, resulting in `28.8px`.
- To summarize, `rem` is relative to the root element's font size, while `em` is relative to the font size of the current or parent element.
- you are not limited to using `em` in font size . you can use it to set padding in reference to the font size of current element 
- 
![[Pasted image 20230619112233.png]]
- use ch to limit the number of character in a line :- `width: 40ch`
- there are certain default values of style that browser set for user . we can view it in inspect function in element tab under styles (heading user style)
- to ensure complete control over the page style . use 
```
`*`{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```
- use `vh` for height . here is one example of where it might be useful
```
body {
  min-height: 100vh;
}
```
-   Using `min-height: 100vh;` on the `body` element ensures that the height of the body will be at least the full height of the viewport.
- The `vh` unit represents the percentage of the viewport height, so `100vh` is equal to 100% of the viewport height. By setting `min-height: 100vh;` on the `body`, you ensure that the body element will take up at least the full height of the viewport, even if its content is smaller.
- This technique is commonly used to create full-height layouts, where you want the body element to fill the entire visible area of the browser window. By using `min-height` instead of `height`, you allow the body element to expand further if its content exceeds the viewport height. This is particularly useful when the content is dynamic or when you want to prevent issues like content overflow or overlapping.
- In summary, `min-height: 100vh;` on the `body` element is often used to create full-height layouts and ensure that the body element always covers at least the full height of the viewport.
## Box model 
- ![[Pasted image 20230619114945.png]]
- here orange shows the margin, green shows the padding and blue represent the content
- inside inspect function select computed tab to see more visualised model with measurements 
- ![[Pasted image 20230619115105.png]]
- In CSS, the `box-sizing` property is used to control how the total width and height of an element is calculated.
- By default, when you specify the width and height of an element, those values only affect the content area of the element. Any padding and border added to it will increase the overall width and height of the element. This default behavior is known as the "content-box" model.
- However, with the `box-sizing` property, you can alter this behavior and define whether the specified width and height should include the padding and border or not.
- There are two possible values for the `box-sizing` property:
	1. `content-box` (default): This value tells the browser to calculate the width and height of an element, including only the content area. In other words, any padding or border added to the element will increase the total size of the element beyond the specified width and height
	2. `border-box`: With this value, the browser calculates the width and height of an element, including the content area, padding, and border. The padding and border are drawn inside the specified width and height, so they don't increase the overall size of the element.
- To use the `box-sizing` property, you would typically apply it to the CSS rule for the desired element or elements. For example:
```css
.box {
  box-sizing: border-box;
  width: 200px;
  height: 100px;
  padding: 10px;
  border: 1px solid black;
}
```
- In the above example, the `box-sizing: border-box;` declaration ensures that the specified width and height of the `.box` element includes the padding and border, resulting in a total size of 200px by 100px.
- By using `box-sizing`, you can have more predictable layouts and easily calculate the dimensions of elements when working with padding and border styles
- margin property is applied in order of top , right ,bottom , left.
- ![[Pasted image 20230619124627.png]]
- outline property :- it wrap around the border 
- outline-offset:- specify how much distance b.w border and outline
- use margin: --rem auto; to center the element horizontally 

## Typography 
- Use inherit value 
- text-decoration
- text-transform
- text-align: justify , equal on both side
- ![[Pasted image 20230619132002.png]]
- notice first line of paragraph
- letter-spacing
- line height
- word-spacing
- use google fonts to import them into css . remember to paste the import link on top of css file

## Links
- try looking into cursor properties
- try text-decoration : none;
- pseudo class
	- In CSS, a pseudo-class is a keyword that is used to select and style elements based on their state or specific relationships to other elements in the document. Pseudo-classes are preceded by a colon (`:`) and added to the end of a selector.
	- Pseudo-classes allow you to apply styles to elements that are not based solely on their element type or class, but rather on additional conditions or states. Here are some common examples of pseudo-classes:
		1. :hover - This pseudo-class is used to select an element when the user hovers over it with the cursor. It's commonly used to change the appearance of links when they are being hovered over.
		    
		2. :active - This pseudo-class selects an element while it is being activated or clicked by the user. It's often used to provide visual feedback when a button or link is being clicked.
		    
		3. :focus - This pseudo-class selects an element that currently has keyboard focus. It's commonly used to apply styles to form elements such as input fields when they are selected.
		    
		4. :first-child - This pseudo-class selects the first child element of its parent. It's useful for targeting and styling specific elements within a container, such as the first item in a list.
		    
		5. :nth-child - This pseudo-class allows you to select elements based on their position within their parent. You can use it to target specific elements in a series, like every other element or every third element.
	     - These are just a few examples, and there are many more pseudo-classes available in CSS. Pseudo-classes provide a way to apply styles based on various conditions, states, or relationships, enhancing the flexibility and interactivity of CSS styling.
 - https://youtu.be/n4R2E7O-Ngo?t=7734 important point discussed here
 - The **`:focus`**  represents an element (such as a form input) that has received focus. It is generally triggered when the user clicks or taps on an element or selects it with the keyboard's Tab key.
## Lists 
- for ordered list 
	- list-style-type
	- use list-style-image :- to use custom points `list-style-image: url("...")`
		- ![[Pasted image 20230619143012.png]]
- nth-child() pseudoclass :- this can be used to change css of certain nth li 
## Pseudo element
-  In CSS, a pseudoelement is a keyword used to style a specific part of an element. Pseudoelements allow you to apply styles to parts of an element's content or structure that are not part of the actual HTML markup. They are denoted by double colons (::) in CSS.
- The most commonly used pseudoelements are `::before` and `::after`. They create virtual elements that appear before and after the content of an element, respectively. These pseudoelements can be used to insert decorative elements or additional content.
- Here's an example of using `::before` to insert content before an element:
```css
.my-element::before {
  content: "Before";
  /* Other styles */
}
```
- And here's an example of using `::after` to insert content after an element:
```css
.my-element::after {
  content: "After";
  /* Other styles */
}
```
- Besides `::before` and `::after`, CSS also provides other pseudoelements, such as `::first-line` (selects the first line of text within an element), `::first-letter` (selects the first letter of text within an element), and `::selection` (selects the portion of text that is selected by the user).
- It's worth noting that in CSS3, the single colon syntax (`:before`, `:after`, etc.) is also valid and widely supported, but the double colon syntax (`::before`, `::after`, etc.) is the recommended syntax in CSS3 and newer versions.
- ![[Pasted image 20230619152649.png]]

## auto in margin
- In CSS, the `auto` value for the `margin` property is used to automatically calculate and distribute the margin space for an element. It is commonly used in horizontal centering of block-level elements within their parent containers.
- When you set the `margin` property of an element to `auto`, the browser will automatically calculate and distribute the remaining space evenly on both sides of the element, pushing it towards the center. This applies to both horizontal and vertical margins, depending on the context.
- In this case, by setting both the left and right margins to `auto`, the element will be horizontally centered within its parent container.
- It's important to note that the `auto` value for `margin` only works in certain cases. It requires a defined width for the element, either through a specific value (`width: 200px;`) or by using other properties like `display: block;` or `display: flex;`. Additionally, `margin: auto` has no effect on elements that are absolutely positioned (`position: absolute;`) or floated (`float: left;`, `float: right;`).
- Using `margin: auto` is a popular technique for centering elements horizontally, but keep in mind that it doesn't apply to vertical centering. For vertical centering, different approaches such as using flexbox or CSS Grid are typically employed.

## Display property
- In CSS, the `display` property is used to control how an element is rendered or displayed on a web page. It defines the type of box or layout model that an element should follow. The `display` property accepts various values, each with its own behavior and purpose. Here are some commonly used values:
	1. `block`: This value creates a block-level element that takes up the full width available and starts on a new line. It ignores any adjacent elements and fills the available horizontal space.
	2. `inline`: This value creates an inline element that only takes up as much width as necessary and does not start on a new line. It respects adjacent elements and allows other inline elements to be on the same line.
	3. `inline-block`: This value combines aspects of both `block` and `inline`. It creates a block-level element that does not start on a new line and allows other inline elements to be on the same line. It respects width and height properties.
		- The `inline-block` value for the `display` property in CSS combines aspects of both `inline` and `block` elements. It allows an element to be displayed inline, meaning it doesn't start on a new line, while also respecting the width and height properties like a block-level element.
		- Here are some key characteristics and behaviors of elements with `display: inline-block`:
			1. Inline Flow: Elements with `display: inline-block` flow within the normal text flow of a document, similar to `inline` elements. They can appear alongside other inline elements on the same line.
			2. Block-Level Properties: Unlike purely `inline` elements, elements with `inline-block` respect the `width`, `height`, `padding`, `margin`, and `border` properties, just like block-level elements. This allows you to set specific dimensions and spacing for the element.
			3. Width and Height: By default, an `inline-block` element will have a width that is determined by its content. However, you can explicitly set the `width` and `height` properties to give it specific dimensions.  
			4. Margin and Padding: `inline-block` elements can have horizontal margins (`margin-left` and `margin-right`) and vertical margins (`margin-top` and `margin-bottom`), which affect their positioning relative to other elements. Padding can also be applied to an `inline-block` element.			    
			5. Line Height: The line height property (`line-height`) affects the spacing of text within an `inline-block` element, just like with `inline` elements.	    
			6. Multiple Elements: When `inline-block` elements are placed consecutively without any white space or line breaks between them, they can create a slight gap or space due to the white space in the HTML markup. This can be addressed by removing the white space between the elements or using other techniques like setting the `font-size` of the parent container to zero.    
		- The `display: inline-block` value is commonly used when you want elements to be positioned inline but still have block-level properties and the ability to set dimensions. It is often used for creating navigation menus, buttons, and other components that need to flow inline but have a defined width and height.
	4. `none`: This value hides the element completely. The element is not rendered, and its space is collapsed. It is commonly used for toggling the visibility of an element dynamically.
	5. `flex`: This value enables a flexible box layout model, known as flexbox. It allows you to control the arrangement and alignment of child elements along a single direction (either horizontally or vertically). It provides powerful features for creating responsive layouts.
	6. `grid`: This value enables a grid layout model, known as CSS Grid. It allows you to create two-dimensional grid-based layouts, defining both rows and columns. It offers advanced control over the positioning and sizing of elements within the grid.
- These are just a few examples of the `display` property values in CSS. There are additional values like `table`, `table-cell`, `table-row`, etc., which are used for creating table-like layouts. The appropriate choice of `display` value depends on the desired layout and behavior you want to achieve for your elements.
- https://youtu.be/n4R2E7O-Ngo?t=9881

## Floats
- In CSS, the `float` property is used to move an element to the left or right of its container, allowing other elements to flow around it. When an element is floated, it is taken out of the normal flow of the document and positioned based on the specified float value.
- ![[Pasted image 20230619170917.png]]
- Here's an example of using the `float` property in CSS:
```html
<div class="container">
  <div class="left">Left Content</div>
  <div class="right">Right Content</div>
</div>
```
```css
.container {
  width: 400px;
}

.left {
  float: left;
  width: 200px;
  background-color: lightblue;
}

.right {
  float: right;
  width: 200px;
  background-color: lightgreen;
}
```

- In this example, we have a container `<div>` with two child `<div>` elements: `.left` and `.right`. The `float` property is used to position them side by side.
- The `.left` element is floated to the left using `float: left;`. It has a width of 200 pixels and a light blue background color.
- The `.right` element is floated to the right using `float: right;`. It also has a width of 200 pixels, but its background color is light green.
- As a result, the `.left` element will float to the left, and the `.right` element will float to the right within the container. Other content following the floated elements will flow around them.
- It's important to note a couple of things about floats:
	1. Parent Container Collapse: When an element is floated, it is taken out of the normal document flow, and the parent container may collapse, resulting in a loss of height. To prevent this, you can use a clearfix technique or apply an appropriate clearing mechanism to the parent container.
	2. use `display: flow-root;` on the container so that problem seen in above picture not happens
- Floats were commonly used for layout purposes in the past, but nowadays, more modern techniques like flexbox and CSS Grid are often preferred due to their more robust and flexible layout capabilities.

## Columns
In CSS, the `columns` property is used to create multiple columns within an element's content area. It allows you to divide the content vertically into a specified number of columns, similar to a newspaper layout.

Here's an example of using the `columns` property in CSS:

```css
.column-container {
  columns: 2;
  column-gap: 20px;
}
```

In this example, the `.column-container` element is divided into two columns using the `columns` property. The content inside the element will flow into these columns.

The `columns` property accepts a value that represents the desired number of columns. In the example above, we specified `2`, which means the content will be divided into two columns. You can also use other values like `3`, `4`, or `auto` to automatically determine the number of columns based on the available space.

In addition to the `columns` property, you can use other related properties to customize the appearance and behavior of the columns:

- `column-width`: This property specifies the desired width of each column. You can set a specific width value (`200px`, `50%`, etc.) or use `auto` to let the browser determine the width automatically.

- `column-gap`: This property sets the gap or spacing between columns. You can specify a value in pixels (`20px`) or other units.

- `column-rule`: This property sets the style, width, and color of a rule (line) between columns. For example, `column-rule: 1px solid #ccc;` will create a 1-pixel solid line between the columns.

- `column-count`: This property allows you to specify the exact number of columns, similar to the `columns` property. However, `column-count` does not automatically adjust the width of the columns; it distributes the content evenly across the specified number of columns.

It's important to note that the `columns` property is not supported in all browsers. It has better support in modern browsers, but older versions of Internet Explorer have limited or no support. To ensure cross-browser compatibility, it's recommended to use CSS layout techniques like flexbox or CSS Grid for creating multi-column layouts, especially for complex layouts or when backward compatibility is required.
- break-inside: avoid ; declaration for avoiding this 
- ![[Pasted image 20230619173113.png]]
- column-span: all;
- ![[Pasted image 20230620052904.png]]
- white-space: nowrap;

## Span
- In HTML, the `<span>` element is an inline-level element used to group and apply styles to a specific portion of text or a small section of content within a larger block of text. It does not inherently have any visual or structural meaning, but it is commonly used to target and style specific elements within a larger context.
## Position
Sure! Here's an explanation of each CSS declaration you mentioned:
1. `position: absolute;`
   - The `position: absolute;` property is used to position an element relative to its nearest positioned ancestor or the containing block.
   - When an element has `position: absolute;`, it is taken out of the normal document flow, meaning other elements will not adjust their position based on it.
   - It can be positioned using the `top`, `bottom`, `left`, and `right` properties to specify its exact location.
   - If no positioned ancestor is found, the element is positioned relative to the initial containing block (usually the viewport).
2. `position: fixed;`
   - The `position: fixed;` property is similar to `position: absolute;`, but the element is positioned relative to the viewport, regardless of scrolling.
   - A fixed-position element remains in the same position even when the page is scrolled.
   - Like `position: absolute;`, it can be positioned using the `top`, `bottom`, `left`, and `right` properties.
3. `position: relative;`
   - The `position: relative;` property positions an element relative to its normal position within the document flow.
   - When an element has `position: relative;`, it can be moved using the `top`, `bottom`, `left`, and `right` properties.
   - Other elements in the document will still occupy the original space of the element being relatively positioned.
4. `position: sticky;`
   - The `position: sticky;` property is used to make an element stick to a specific position as the user scrolls the page.
   - A sticky-positioned element behaves like `position: relative;` until it reaches a specified scroll position (the "sticky" point), where it becomes fixed until scrolling passes the sticky point.
   - it remains sticky to its group elements
```
lets say you want to apply sticky position to a nav bar , the nav bar will stick to top position until its scope in html code remains. meaning the moment nav tag is closed this position will not be applied.
```
   - https://youtu.be/NzjU1GmKosQ?t=270
1. `z-index: 1;`
   - The `z-index` property controls the stacking order of positioned elements.
   - It specifies the element's stack level, determining how it overlaps with other elements.
   - A higher `z-index` value places an element in front of elements with lower `z-index` values.
   - Elements with the same `z-index` value are stacked according to their order in the HTML structure.
Regarding `scroll-behavior: smooth;`, it is not a positioning property but rather a CSS property used in HTML. It is used to control the scroll behavior when a user navigates to a different part of a web page by clicking an anchor link or using JavaScript to scroll.
- By setting `scroll-behavior: smooth;` on the `html` or `body` element, the scrolling will be animated and have a smooth transition effect.
- When a user clicks on an anchor link that points to an element on the same page, the scrolling action will be smooth and animated rather than an immediate jump to the target position.

## Supports
The `@supports` rule is a CSS feature query that allows you to apply styles based on whether a particular CSS property or feature is supported by the user's browser. It provides a way to write CSS code that is compatible with different browser capabilities.

The basic syntax of `@supports` rule is as follows:

```css
@supports (condition) {
  /* CSS rules to apply if the condition is true */
}
```

Here, `condition` represents one or more CSS property checks or feature checks that you want to test. If the condition is true, the CSS rules within the `@supports` block will be applied; otherwise, they will be ignored.

For example, let's say you want to use the `grid` layout, but you want to provide an alternative layout using `float` for browsers that don't support CSS Grid. You can use `@supports` to check if the browser supports `display: grid` and apply different styles accordingly:

```css
@supports (display: grid) {
  /* CSS rules for browsers that support CSS Grid */
  .container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 20px;
  }
}

@supports not (display: grid) {
  /* CSS rules for browsers that don't support CSS Grid */
  .container {
    float: left;
    width: 50%;
  }
}
```

In the above example, if the browser supports `display: grid`, the styles within the first `@supports` block will be applied. Otherwise, if it doesn't support `display: grid`, the styles within the second `@supports` block will be applied.

The `@supports` rule can also be used with complex conditions by combining multiple property checks using logical operators such as `and`, `or`, and `not`. Here's an example:

```css
@supports ((display: grid) and (grid-template-columns: 1fr)) {
  /* CSS rules for browsers that support CSS Grid with 1fr columns */
}

@supports (not (display: grid) or (float: left)) {
  /* CSS rules for browsers that don't support CSS Grid or support float: left */
}
```

By using `@supports`, you can write more robust and future-proof CSS code that adapts to different browser capabilities and ensures a consistent user experience across a wide range of devices.

## Flex box
Flexbox, short for Flexible Box Layout, is a CSS layout module that provides a flexible way to create responsive and dynamic layouts. It is designed to efficiently distribute space and align elements within a container, regardless of their size or order.

https://www.flexboxfroggy.com for more practice

To use flexbox, you need to apply it to a container element, referred to as the flex container, and define its properties. Here's an overview of the key concepts and properties involved in flexbox:

1. Flex Container:
   - To create a flex container, you need to set the `display` property of the container element to `flex` or `inline-flex`. This enables the flexbox behavior for its child elements.

2. Flex Items:
   - Flex items are the child elements of a flex container.
   - By default, flex items are laid out in a single row (`flex-direction: row`), but you can change the layout direction by modifying the `flex-direction` property.

3. Main Axis and Cross Axis:
   - Flexbox layout is based on two axes: the main axis and the cross axis.
   - The main axis is determined by the `flex-direction` property and defines the primary direction of the flex items.
   - The cross axis is perpendicular to the main axis.

4. Flex Properties for Flex Items:
   - `flex-grow`: Determines how flex items grow to fill the available space along the main axis.
   - `flex-shrink`: Controls how flex items shrink when there is not enough space along the main axis.
   - `flex-basis`: Specifies the initial size of flex items before any available space is distributed.
   - `flex`: A shorthand property that combines `flex-grow`, `flex-shrink`, and `flex-basis` in one declaration.
   - `order`: Specifies the order in which flex items appear within the flex container.

5. Alignment and Distribution:
   - `justify-content`: Aligns flex items along the main axis and controls the horizontal alignment within the flex container.
   - `align-items`: Aligns flex items along the cross axis and controls the vertical alignment within the flex container.
   - `align-content`: Aligns flex lines along the cross axis when there is extra space on the cross axis.

Flexbox provides a flexible and powerful way to create various types of layouts, including single-row or single-column layouts, equal-height columns, vertical centering, and more. It simplifies responsive design by automatically adjusting the layout based on available space.

Flexbox is well-supported in modern browsers, making it a popular choice for creating responsive web layouts. It offers a more intuitive and straightforward approach to layout design compared to traditional CSS methods.

1. `justify-content`:
   - The `justify-content` property is used in flexbox layouts to align and distribute flex items along the main axis of the flex container.
   - It controls the horizontal alignment of flex items and accepts various values such as `flex-start` (aligns items to the start of the container), `flex-end` (aligns items to the end), `center` (centers items), `space-between` (distributes items evenly with the first item at the start and the last item at the end), `space-around` (distributes items evenly with equal space around them), and `space-evenly` (distributes items evenly with equal space around and between them).

2. `align-items`:
   - The `align-items` property is used in flexbox layouts to align flex items along the cross axis of the flex container.
   - It controls the vertical alignment of flex items and accepts values such as `flex-start` (aligns items to the start of the container), `flex-end` (aligns items to the end), `center` (centers items), `baseline` (aligns items based on their baselines), and `stretch` (stretches items to fill the container).

3. `flex-direction`:
   - The `flex-direction` property specifies the direction of the flex container's main axis and the order in which flex items are laid out.
   - It accepts values such as `row` (items are laid out horizontally in a row), `row-reverse` (items are laid out horizontally in reverse order), `column` (items are laid out vertically in a column), and `column-reverse` (items are laid out vertically in reverse order).

4. `flex-wrap`:
   - The `flex-wrap` property specifies whether flex items should wrap onto multiple lines if they exceed the width or height of the flex container.
   - It accepts values such as `nowrap` (items are not wrapped and will be displayed in a single line), `wrap` (items wrap onto multiple lines if necessary), and `wrap-reverse` (items wrap onto multiple lines in reverse order).

5. `flex-flow`:
   - The `flex-flow` property is a shorthand for specifying both `flex-direction` and `flex-wrap` in a single declaration.
   - It combines the two properties and accepts values such as `row nowrap` (items are laid out horizontally in a single line without wrapping), `column wrap` (items are laid out vertically in multiple lines with wrapping), etc.

6. `align-content`:
   -  use `align-content` to set how multiple lines are spaced apart from each other. This property takes the following values:
	- `flex-start`: Lines are packed at the top of the container.
	- `flex-end`: Lines are packed at the bottom of the container.
	- `center`: Lines are packed at the vertical center of the container.
	- `space-between`: Lines display with equal spacing between them.
	- `space-around`: Lines display with equal spacing around them.
	- `stretch`: Lines are stretched to fit the container.
	- This can be confusing, but `align-content` determines the spacing between lines, while `align-items` determines how the items as a whole are aligned within the container. When there is only one line, `align-content` has no effect..

7. `flex-basis`:
   - The `flex-basis` property specifies the initial size of a flex item along the main axis before any available space is distributed.
   - similar to min width
   - It determines the default size of the item before any growing or shrinking occurs.
   - It accepts values like `auto` (default, item's size is based on its

## Grid layout

## img 
- images are not block level element but are inline element 
- by setting the display setting of image to block it can be changed 
- use percentage width to make it responsive 
- background-image: url('bg.jpg');background-repeat: no-repeat;background-size: cover;
- text-shadow
- https://youtu.be/n4R2E7O-Ngo?t=18873 important
- to create circle image use it in square dimension and make the border radius to 50%
- background-position : 
- background-image: liner-gradient ` background-image: linear-gradient(steelblue, purple , white);`
- ` background-image: linear-gradient(to left ,steelblue, purple , white);`

## Min Max and clamp
- min function look for smallest of the argument provided `min(500px,70%)`
- max function look for maximum of the argumeent provided `max(500px,70%)`
- use can also pass one of these function as argument inside other function `min(max(), 500px)`

In CSS, the `clamp()` function allows you to define a range of values and specify a value that should be within that range. The `clamp()` function takes three arguments: a minimum value, a preferred value, and a maximum value. The function will return the preferred value if it falls within the specified range; otherwise, it will return the closest boundary value.

Here's an example of how you can use `clamp()` in CSS:

```html
<style>
  .container {
    width: clamp(200px, 50%, 400px);
    /* Explanation:
       - The minimum value is 200px.
       - The preferred value is 50% of the parent container's width.
       - The maximum value is 400px.
       - The resulting width will be the preferred value if it falls between 200px and 400px.
         Otherwise, it will be clamped to the closest boundary value.
    */
  }
</style>

<div class="container"></div>
```

In the example above, the `width` property of the `.container` class is set using the `clamp()` function. The preferred value is specified as 50% of the parent container's width. If the parent container's width is within the range of 200px to 400px, the preferred value will be used. Otherwise, the width will be clamped to either 200px or 400px, whichever is closest.

Note that the `clamp()` function is widely supported in modern browsers, but it may not work in older browser versions. It's always a good idea to check the browser compatibility before using new CSS features.