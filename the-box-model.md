# The Box Model
The CSS Box Model is a concept that basically boils down to every HTML element has a box around it. The Box Model with content in the innermost layer, padding wrapped around it, a border wrapped around the padding, and margin as the outermost layer.

# Default box settings
- With elements (boxes) that have a display value of "block", either because it is the default value for that kind of element (i.e., div elements, headers, and p elements) or because it is specifically overridden in the CSS, the browser follows these rules to layout the element:

    - The box fills available container space, and in most cases it fills up 100% of the available space, becoming as wide as its container.
    - Each new box appears on a new line/row.
    - The CSS properties width and height are respected.
    - The padding, margin and border of the box will push other elements farther away from the box.

- With elements (boxes) that have a display value of "inline", either because it is the default value for that kind of element (i.e., span, a, and img elements) or it is specifically overridden in the CSS, the browser follows these rules to layout the element:

    - Each box appears next to each other in a single line until it fills up the available space.
    - The CSS properties width and height don't apply.
    - The padding, margin and border of a box are applied, but they don't push other inline boxes - away from the box.

    # References
    If you are unsure, refer to MDN's "list of inline elements" and "list of block elements"


# Standard Box Model vs. border-box
In the standard Box Model, the width and height of an element set with CSS refers to the width and height of the box's content. Any padding, border and margin added to the element will get added to the total size of actual box. If padding, border or margin are removed from a box, the box size decreases, but the width and height of the content stays the same.

        .box {
            border:  10px solid black; /* Applies to all four sides. */
            height:  100px; /* Content's height */
            margin:  50px;  /* Applies to all four sides. */
            padding: 25px;  /* Applies to all four sides. */
            width:   250px; /* Content's width */
        }

In CSS version 3, the box-sizing property was added to the CSS specification which allows you to set it to the values "content-box" (which is how it is by default) or "border-box", which does what most Web developers want. Setting the box-sizing property to border-box includes the width of the left border, right border, left padding, and right padding in the overall width, and the top border, bottom border, top padding, and bottom padding in the overall calculation of the height.

        .box {
            border:  10px solid black; /* Applies to all four sides. */
            box-sizing: border-box;
            height:  100px; /* Sum of content + top/bottom padding + top/bottom border */
            margin:  50px;  /* Applies to all four sides. */
            padding: 25px;  /* Applies to all four sides. */
            width:   250px; /* Sum of content + left/right padding + left/right border */
        }


# Padding
.box-1 {
  /* One value applies to all four sides. */
  padding: 3em;
}

.box-2 {
  /* Two values: top & bottom | left & right */
  padding: 20% 5%;
}

.box-3 {
  /* Three values: top | left & right | bottom. */
  padding: 15px 10px 20px;
}

.box-4 {
  /* Four values:  top | right | bottom | left*/
  padding: 0 10px 2em 1em;
}

.box-5 {
  /* Global values */
  padding: inherit;  /* OR initial OR unset */
}

# Border
Border is a shorthand CSS property that sets an element's border on all sides. It sets the values of border-width, border-style, and border-color (in that order).

.box {
  border: 3px solid #000000;
  /* border-width | border-style | border-color */
}

# Properties within the shorthand
- border-width:
    - border-top-width
    - border-right-width
    - border-bottom-width
    - border-left-width
- border-style:
    - border-top-style
    - border-right-style
    - border-bottom-style
    - border-left-style
- border-color:
    - border-top-color
    - border-right-color
    - border-bottom-color
    - border-left-color

# Margin
Margin is a shorthand CSS property that sets the margins on every side of an element. It encompasses margin-top, margin-right, margin-bottom, and margin-left.

Like padding, margin values can be a length (i.e. px, em, rem) or a percentage (%). It can also take a value of auto.

.box-1 {
  /* One value applies to all four sides. */
  margin: 10%;
}

.box-2 {
  /* Two values: top & bottom | left & right */
  margin: 0 2em;
}

.box-3 {
  /* Three values: top | left & right | bottom. */
  margin: 30px 0 15px;
}

.box-4 {
  /* Four values:  top | right | bottom | left*/
  margin: 10% 20px 10px 5%;
}

.box-5 {
  /* Global values */
  margin: inherit;  /* OR initial OR unset */
}

# Centering an element with margin
With the auto value, the browser sets the margin for an element. We can apply this property to horizontally center an element inside its parent container.

.box-parent {
  background-color: #000000;  /* Black */
  width: 300px;
  height: 300px;
}

.box-child {
  background-color: #ffff00;  /* Yellow */
  width: 100px;
  height: 280px;
  padding: 10px;
  margin: 0 auto;  /* Centers element horizontally. */
}



