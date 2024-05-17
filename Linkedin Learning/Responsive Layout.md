# Basic Page Structure

## Meta element

By default, browsers assume the webpage is *not responsive* 

viewport: non-minimized area of a browser window.

'content="width=device-width, initial-scale=1"'

### `"width=device-width"`

We tell the browser the width of our page is the same as our device's width.

### initial-scale=1
The website will not be zoomed in or out.

#### Don't use:
user-scalable
minimum-scale
maximum-scale

## Required CSS

HTML page has default CSS settings applied to it.

### Box model

Every HTML element is represented as a rectangular box on the page

The content of the element is the element itself. Beyond it is the padding. Then border. Then margin. 

Margin is independent of the content-size of the element.

### Let's take a div element

#### If an element has a set width,

By default, the padding, margin, and border are added outside the div.

By default, the value of **box-sizing** is *content-box*, which results in the behavior above (line 36).

Change it to border-box. This will include the padding and the border sizes to its content size.

For instance, we have div element with the width of 800px for its content, 10px padding and border.

This results in 840px of the whole element. 

If we change the box-sizing of the div to border-box. Its content size is now 760px, while the rest stay the same. 

This results in 800px of the whole element.

### Assign box-sizing to border-box, always.
	html{
	box-sizing:border-box;
	}

And to make the elements inherit the box-sizing of their parent,
	asterisk, asterisk:before, asterisk:after{
	box-sizing:inherit;
	}

### max-width for images
by default, images display their actual size on a webpage.

While it looks good on your wide-ass screen, you'd have to scroll sideways on your phone.

#### Solution:
img{
max-width:100%;
}

When you give a max-width of 100% to an element, its size will never be wider than the width of its parent element. 

The parent element here is the 'body' element.

## Display property

Specifies the type of box to display the element in.

**Values**
	display:inline;
	display:inline-block;
	display:block;
	display:flex;
	display:grid;

Every element in a page will start out as a rectangle. 

**inline**
	An element that is in line with other text and doesn't break the flow of text.
	Can add 'margin' and 'padding' to the element, but only horizontally.
	Will also ignore a 'height' or 'width' attritbute.
	Examples: 'span', 'em', 'strong'

**block**
	An element that takes up a block of area on the page.
	Examples: 'h1', 'p', 'div', 'section', 'nav'
	By default, take up the full width of its parent element. Width can be changed.
	By default, will always start on a new line.

**inline-block**
	Element appears inline but can be given width or height, but will stay in line.

**flex and grid**
	Affect how the elements inside (children) are displayed. 

## When creating an HTML page,

Imagine a user is only getting the text, use this to determine what order everything should go in.

Like: Header at the top, followed by the main content, then supplementary content, then you can use CSS to arrange them visually.

## Positioning

Use to move different elements on a page.

**Values**
	position:static;
	position:relative;
	position:absolute;
	position:fixed;
	position:sticky;

**static**
	Default position. It is where it is in the normal flow of the page. 
	Cannot use 'left', 'top', 'right', 'bottom'.

Other values will allow the element to move around.

**relative**
	Similar to static, but it can use `top, left, bottom, right` properties. 
	When using these properties, it moves **relative** to its original position. So using `left` will move the element to wards the right, **based on its original position**.

'**left', 'top', 'right', 'bottom'** properties move the elements away from that direction. 
	Example: 'left' will move the element away from the left, therefore going towards right.
	Can use negative values to move toward that direction.

**absolute**
	- Element is taken out of the normal flow of the page. I.e. the document will no longer include this element in its size calculations, and how elements are typically arranged. **But it will hover to where it originally is**.
	- Only as wide as its content, rather than being as wide as the parent for `div`s.
	- Using `top, right, bottom, left` properties will position the element inside the first non-static ancestor or `html` tag if none.
	- Using `left` and `right` positions will move the element `n` to the right or left, but its vertical coordinates are based on its original position pre-absolute.


**fixed**
	- Taken out of the normal flow of the page.
	- Positoned on the whole page. Stays in that position even when scrolling. 
	- Example: **fixed** element placed on (40,40) of the viewport, it will always stay in that (40,40) of the viewport even when scrolled.

**sticky**
	- Not taken out of the normal flow.
	- Will stick to the specified `top, left, bottom, right` even if the user scrolled passed the element in question.
	- Example: Element with **sticky** and **top:40px;**. If the user scrolled passed the element, it will retain its shape from the normal flow of the page, but it will always stick on the screen with **40px** off the **top**.

An element with non-static position will always be in front of static-positioned elements

### Z-index
Sets the z-axis order of a non-static element.

Can only be applied to non-static elements. 

Positve number to come in front, negative to come behind.

Higher numbers go in front of lower numbers.

By default, elements have a z-index of **auto**. Static elements are on the page first, in the order that they are defined, non-static elements are on top of these static ones, in the order they are defined. 

This means that if you have 2 non-static elements, the 2nd non-static element will be on top of the 1st one. Same principle to the static elements.



## Floats
"Back in my day, we used floats instead of flexbox and grids."

Places an element along the left or right side of its container while respecting the normal flow of the page, and allowing other elements to take the empty width in the taken Y-axis of the floating element.

**clear**
	- Sets an element to be placed below the floating element.
	- This makes the element in question act as if the floating element were not floating.
	- Values:
		clear:left;
		clear:right;
		clear:both;
	-Clear value must match the floating element's float value.

## Units
Set an element's width and height.

**Pixel**
	- Smallest controllable point of color on a screen.
	- On a desktop monitor, around 1/96 inch, or .26mm.
	- Will always be the same size no matter what  you do with your code.

Relative units mean their length can vary. And the contents will fit at any size viewport. Below are such:

**Percent**
	- Based on the height or width of the container element if setting the height or width respectively.

**Viewport Width and Height or VW and VH** 
	1/100th of the viewport width/height

VMIN
	1/100th of the smaller side of the viewport (in absolute units).

VMAX
	1/100th of the larger side of the viewport (in absolute units).

**fr**
	- Only used in grid layout.
	- Uses a fraction of the leftover space in the container.

# Responsive Layout
Used in every site you create.

(1) Looks good on different sizes and is (2) usable on as many devices as possible.

(1) Use of **media query** 
(2) Even if the user uses outdated software, the should still be able to perform the task they want.

**2 Traits that make a site responsive**
	- Flexible 
		Elements can change size depending on the size of the viewport.
	- Adjustable
		- Elements change their layout depending on the size of the viewport.
		- Example: Navigation bar becoming a menu to expanding fully when the viewport is wide enough.

Think about people with disabilities (???)

## Media Queries
Change the layout of the page depending on the viewport

Example: Adjust line length to make sure it looks good on any viewport size.

Media query modifies the site depending on qualities such as viewport size or device type. The answer is determiend whether the CSS is applied when rendering the page.

Example:
	@media (min-width:600){
	body{
		background-color:blue;}
	}
This rule will apply if the query is True.

The browser reevaluates the CSS as you change the size of the browser window.

**Media Queries values** 
	min-width
		if the minimum width of the viewport is at least the specified width or wider, then True.
	max-width
		if the maximum width of the viewport is less or equal to the specified width to be True.

These refer to the width of the viewport, not the screen. This means if you are in a laptop with the browser window minimized, it will display its 'mobile' layout.

There's also a media query about screen width.

**Media queries are evaluated independently**
	If there is an overlapping rule, the one declared at a later point will overwrite the previous rule, but non-overlapping rules will apply at the same time

Example:
@media (min-width: 900px) {
	body { 
		background-color: gray; 
	} 
}
@media (min-width: 600px) {
	body { 
		background-color: blue;
	}
	p {
		color: red;
	}
}

The text color **red** will apply when the width is over 900px.

When designing from **narrow to wider**,
	Use min-width, and put the **smaller** screen styles **first**.

When designing from **wide to narrow**,
	Use max-width. **Bigger** screens **first**.

## Flexbox and Grid

**Flexbox**
	Arranges the elements in one-dimensional, only either horizontal or vertical. Not both.

**Grid**
	Arranges the elements horizontally or vertically.

Apparently you can use float and positioning, but they are better suited for individual items.

## Accessibility
Think about laying out the page in a logical order.

Be able to navigate a page using a keyboard.

i.e. hidden links that become visible when the user enters the tab key

**Tab Order**
	- The order in which elements receive focus when the user tabs through the page.
	- Goes left to right in top to bottom.

Basically, the webpage follows elements in the way they are coded in the HTML, regardless how CSS changes their position.

Example:
	5 clickable elements 'one' through 'five'. The HTML order is: one, two, three, four, five. But with CSS,: five, one, two, four, three.
		- Tabbing will work based on the HTML code, regardless of CSS. This makes navigation confusing.
		- I want to be able to highlight texts 'two' and 'four'. But it selects 'three' instead of 'four' because four is where three is supposed to be (???)

**order** property was used here. order: -1 on 'five' and 1 on 'three'.

Goal of a responsive layout is to make it usable for all users.

## Browser Support
Some outdated devices don't have support for Flex or Grid.

Use **browserstack.com** to test your website across different devices and browsers.

Use **feature queries**. They check whether the browser supports a CSS rule like grid.

# Grid Layout
When you set **display: grid;** the element becomes a grid **container**. Its children become grid **items**.

**Grid Line**
	Lines that contain the columns and rows. Like the 4 sides of a chess board area.
	![[grid-concepts.svg]]

Grid lines follow the LTR or RTL formal of the document.

When you use **grid-template-rows or columns**, the grid lines created = rows or columns + 1
Example:
	```grid-template-columns: repeat(3, 100px);```
		  This creates (3 + 1) amount of grid lines in the column.
	```grid-template-rows: repeat(1, 100px);```
		  This creates (1+1) amount of grid lines in the row.

You can place a grid item by calling their line number. 
```
HTML
	<div class="wrapper"> 
		<div class="item"> Item </div>
	</div>
```

```
CSS
	.wrapper {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		grid-template-rows: 100px 100px;
	}
	.item {
		grid-column-start: 1;
		grid-column-end: 3;
		grid-row-start: 1;
		grid-row-end: 3;
	}
```

You can name the lines before or after their track sizes as well.
```
HTML
	<div class="wrapper">
		  <div class="item">Item</div>
	</div>
```

```
CSS
	.wrapper {
		display: grid;
		grid-template-columns: [col1-start] 1fr [col2-start] 1fr [col3-start] 1fr [cols-end];
		grid-template-rows: [row1-start] 100px [row2-start] 100px [rows-end];
	}
	.item {
		grid-column-start: col1-start;
		grid-column-end: col3-start;
		grid-row-start: row1-start;
		grid-row-end: rows-end;
	}
```

**Grid Track**
	Space between the first and last grid lines grid lines.
	Essentially the collective area between the first line and the last line of a given dimension. 

**Grid Cell**
	One unit in the grid, between opposing row and opposing column grid lines. 

**Grid Area**
	A grid cell or multiple grid cells.


## First, defining rows and columns
First, tell the browser it's a grid, then we can define the rows and columns

**display:grid;**
	Defines the element as a grid container, and its children become a grid item.

We get 1 row and column by default. The amount of rows by default depends on the amount of block elements one the page.

**grid-template-columns**
	Defines the amount of columns in a grid and its sizes.

In the exercise file:
	- We want 2 columns with the sizes 200 and 100px.
		```grid-template-columns: 100px 200px;```
	- Since there are 2 columns but 12 grid items, the grid items will wrap after filling the 2 columns before starting in a new line.

**Explicit Tracks** 
	Lines and tracks created by CSS.

Implicit Tracks
		- Lines and tracks created by the browser for leftover grid items. This is in cases there are more grid items than specified grid tracks
	- Example:
		- In Exercise 3-2 start, the 10 grid items are implicit grids since we only told the browser to create 2 columns and 1 row (by default).
		- Height is based on their content size, width is default i.e. a block element will have a width 100vw (ignoring scrollbar). Follows width sizes by template-columns but not rows.

You can see the explicit grid as **dashed** lines and implicit as **dotted**.

In firefox, the main axis of the **grid-template**, the start and end point of the **defined** track are outlined as a single line, as well as the start point of the cross axis of the defined track, but not the end point.

Chrome outlines the outermost lines but everything is a dashed line. 

**grid-template-rows**
	Defines the rows of the grid

## Grid gap
Add spaces between columns and rows

**grid-gap**
	- Shorthand of **grid-row/column-gap**. This means it can take 2 arguments.
	-1 argument will apply the size to both dimensions.
	- Takes pixel, em, % as measurements.

## Sizing rows and columns
Generally, the keyword 'auto' tells the browser to take up all the available space.

**auto**
	- Set a grid-template-rows/columns. 
	- Works like flex items having 'flex: 1 0 max-content;'.

**fr**
	- Fractional unit.
	- Kind of like a flex item with 'flex: 1 1  min-content;'.
	- When setting a template-row without the container having a height, 1 fr in a row is based on the applied content's height, and the rest is a multiple of that.
	- Implicit grids are probably subtracted when calculating the fr.

**repeat() function**
	Syntax: grid-template-columns: repeat(number of repeat, size to repeat);
	Example: grid-template-rows: repeat(3, 1fr);
	- Can also repeat different sizes.
		Example: grid-template-columns: repeat(2, 1fr 20px);

## Placing grid items
They don't have to display in the order of the HTML, and they don't have to take up 1 cell only.

To place an item on a grid cell, specify the location to place.

In the Dev tools (inspect element), you can see the grid line numbers, positive and negative.

Negative numbers count starting from -1 on the **end** of its cross axis. In the picture, there are 3 explicit columns and the negatives are written on the right side of the rows.
![[grid lines.png]]

Using negative numbers can place grid items on the last grid cell.

`grid-column-start`
	set the horizontal starting location of a grid item. Ends on the same grid line it started by default.

`grid-column-end`
	set the horizontal ending location of a grid item if you want to take more than 1 cell

moving through grid columns leave an empty space so as not to lose "html order", to circumvent:
grid-auto-flow
	Value: `dense`
	Used on the container

grid-column
	shorthand of grid-column-start/end combined.
	Example:
		```grid-column-start: 2;
		grid-column-end: 4;
		grid-column: 2 / 4;```

grid-column-start/end are placing the grid items if they are independent of each other.

if  you don't know the name of where the grid item is supposed to end, you can use:
	`grid-column: 2/span 2;`
	Untested if ```span 2``` is a valid argument for `grid-column-end`

These work for `grid-row-start/end` as well.

`grid-row` is the row equivalent of `grid-column`.

`grid-row` and `grid-column` can be used together to take up 4 cells (2 in each axis) instead of the default 1.

"If you only tell the browser the starting OR ending point of the grid item, it will find the next available space that meets the requirements (i.e no item is explicitly placed there???). If you specify both, it will explicitly follow the it (i.e. overlap if there is an item???)"

`grid-area`
	shortcut for grid-row/column-start, grid-row/column-end. 
	These are 4 separate values.
	Separate each value by slashes (/).

## Grid alignments

`justify-content`
	- Applied to the container
	- Default value: `auto
	![[grid_j-c.png]]

`align-content`
	- Applied to the container
	- Only works when the container's height is higher than its contents' (grid items).
	- By default, the container's height is determined by the height of its grid items.
	![[grid_a-c.png]]

`justify-items`
	- Columns with varying widths can be placed either at the start of the column, end, or center. 
	- By default, it will stretch the item.
	![[grid_j-i.png]]

`align-items`
	- Positions the item vertically within each row.
	- By default, it will stretch the item.
	![[grid_align-items.png]]

`justify-self`
	- Applied on the grid item.
	- Overwrites `justify-items` rule of the container.
	![[grid_j-s.png]]

`align-self
	- Applied on grid items.
	- Overwrites `align-contents` rule of the container.
	![[grid_a-s.png]]

## Variable Columns

`auto-fit` - Grid-template-x determined by the amount of grid items aka the amount of content you have. They do not create new grid-template-x when the size changes, but they do try to fit any excess content.
![[LiL-autofit_ex.png]]

`auto-fill` - Grid-template-x determined by the size of the viewport. If you have space for a new min-size of the X, it will create new X, even if there is no content. Only when it's set to `repeat()`.
![[LiL-autofill_ex.png]]

## Grid template areas

`grid-template-areas
	Defines areas of the grid that can be referenced by name.

Naming starts from the top left of the highest row. 

The named cells CANNOT be L-shaped. 

"You have to name the same amount of cells in each row, else the browser ignores the whole thing."

This means you can't name 3 cells in 1 row and 2 in the other.

The rows are separated by quotation marks (" ")

Example:
	```grid-template-areas: "and im fine" "just burning my" "way toa spotlight"```
	This is the same as:
	```grid-template-areas: 
	"and im fine" 
	"just burning my" 
	"way toa spotlight"```
	But this way is incorrect:
	```grid-template-areas: 
	"and im fine" 
	"just burning my" 
	"way to a spotlight"```

To put an item to the named cell, just reference the named cell to the selected item:
![[LiL-grid-tmp-ar_ex.png]]

If a named cell takes 2 cells, placing the item to that named cell will make it span as long as its taken area.
![[LiL-grid-tmp-ar_ex-2.png]]

If you don't want to give a name to a cell, you can place a period (.).

## Naming grid lines

You can name grid lines in `grid-template-x`.

Example:
	`grid-template-columns: [name1] 100px [name2] 100px [name3] 100px;

Example 2: 
	![[LiL-grid-names_ex.png]]

## Ordering Grid items

`order`
	change order of grid items in the container.

Default `order` value of elements is 0. The highest order element will be the last, and the least will be the first, in the order of the HTML if there are multiple equal values.
Web pages are displayed in the order of the HTML. 
![[LiL-order-g-i_ex.png]]

After `order
![[LiL-order-g-i_ex2.png]]


## Grid flow and implicit tracks

We can set size of implicit tracks

`grid-auto-rows
	Sets the size of auto-generated rows.
	![[LiL-grid-a-r_ex.png]]
	The 3 implicit rows are now sized 100px in height.
	If you set it to`1fr`, all rows (explicit included) will now be 1fr. 1fr is based on the height of the tallest element.
	![[LiL-grid-a-r_ex2.png]]

`grid-auto-flow
	Sets how the grid item flow through the grid.
	 By default, items fill each row going from left to right.
	 With `grid-auto-flow`, you can make it fill by columns instead.
	 Like setting `flex-direction` to column.

Example:
	![[LiL-grid-a-f_ex.png]]
	There are 3 and 2 explcit columns and rows. Every column is filled with the amount of explicit rows available. This in turns create implicit grid columns but no implicit rows.


`grid-auto-columns
	Sets the width of implicit columns. Unless it's `fr`, then it's shared.
	Width is determined by the `min-content` of the longest word of the grid item.

Example:
	![[LiL-g-a-c_ex.png]]
	Since it's `fr`, the sizes are shared and the width is based on the longest between 'thirteen' and 'fourteen'.

You can also use the value `dense` along side `row` or `column`.

Example:
	`grid-auto-flow: column dense;


# Flex Layout

Flexbox can only display its direct children as columns or rows. Not both.

## Defining a flex container

`display:flex;` to the parent whose children you want to become flex items.

By default, item sizes on the main axis are as big as their `min-content` size. And the flex parent's width always fills the width of the viewport.

By default, the cross axis of items is stretched. This means that in a flex `row`, the items' height is as tall the container. In a `column`, they are as wide as their container.

## Direction

`flex-direction
	Define direction of main axis.
	![[LiL-flex_m-a-r.png]]
	![[LiL-flex_m-a-c.png]]

There are four directions:
![[LiL-flex_f-d.png]]
`row`,`row-reverse
`column`,`column-reverse