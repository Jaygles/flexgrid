#Flex Items

There are two main element types:

`.flex-parent` and `.flex-child`

<br>

Classes are meant to be applied to one element type or the other, but not both.

<br>

___

<br>
#Breakpoints

The main media queries are controlled by the breakpoint variables.

###Breakpoint Variables:
`@breakpoint-small` - 320px

`@breakpoint-small` - 768px

`@breakpoint-small` - 960px

<br>

###Media Queries:

`@small` - ( _max-width: breakpoint-small_ ) [__up to 320px__]

`@medium` - ( _min-width: breakpoint-small_ ) and ( _max-width: breakpoint-medium_ ) [__320px - 768px__]

`@large` - ( _min-width: breakpoint-medium_ ) and ( _max-width: breakpoint-large_ ) [__768px - 960px__]

`@xlarge` - ( _min-width: breakpoint-large_ ) [__960px and up__]

<br>

These four size names ( __small__, __medium__, __large__, __xlarge__ ) can be concatenated into the other classes.

<br>

___

<br>
#Width


This is a 12 grid system. To set the width of a flex-child element across all media sizes:

`.flex-width-1` - occupies <sup>1</sup>/<sub>12</sub> of the flex-parent width ( __8.333%__ )

`.flex-width-2` - occupies <sup>2</sup>/<sub>12</sub> of the flex-parent width ( __16.666%__ )

`.flex-width-3` - occupies <sup>3</sup>/<sub>12</sub> of the flex-parent width ( __25%__ )

`.flex-width-6` - occupies <sup>6</sup>/<sub>12</sub> of the flex-parent width ( __50%__ )

`.flex-width-12` - occupies <sup>12</sup>/<sub>12</sub> of the flex-parent width ( __100%__ )

<br>

As stated above, each of the four size names may be concatenated into the classes:

`.flex-small-width-12` - occupies 100% of the flex-parent width on small media

`.flex-medium-width-6` - occupies 50% of the flex-parent width on medium media

`.flex-large-width-3` - occupies 25% of the flex-parent width on large media

`.flex-xlarge-width-1` - occupies 8.333% of the flex-parent width on xlarge media

<br>

We can combine all of these classes to easily create a responsive layout. It is important to order classes from smallest to largest (mobile-first):

```
<div class="flex-parent">
  <div class="flex-child flex-small-width-12 flex-medium-width-6 flex-large-width-3 flex-xlarge-width-1">
  </div>
</div>

```
<br>
Larger sizes do not override smaller sizes. Generic classes (`.flex-width-4`) will override sized classes (`.flex-small-width-6`) if they are placed later in the order. So, place generic classes at the beginning to set styles that only take effect if you have not used more specific sized classes for that breakpoint. For example:

```
<div class="flex-parent">
  <div class="flex-child flex-width-6 flex-small-width-12 flex-xlarge-width-3">
  </div>
</div>
```
Now, `.flex-width-6` will only apply at the medium and large breakpoints, because it has not been overriden.

<br>

___

<br>
#Order


These classes can be applied to increase or decrease the order in which flex-child items will appear within the flex-parent. Decreasing the order causes the item to appear earlier, while increasing the order causes it to appear later.

`.flex-order-neg-1` - decrease flex-child order by 1

`.flex-order-neg-12` - decrease flex-child order by 12

`.flex-order-pos-1` - increase flex-child order by 1

`.flex-order-pos-12` - increase flex-child order by 12

<br>

```
<div id="one" class="flex-child flex-order-pos-2"></div>
<div id="two" class="flex-child flex-order-neg-1"></div>
```
In this example, `div#two` will appear before `div#one`.

<br>

The maximum value for order-pos or order-neg is 12 and the minimum is 1.

<br>

___

<br>
#Grow and Shrink


These classes can be applied to allow flex-child elements to grow or shrink to fill the flex-parent. Flex-child elements will not grow at all until a `.flex-grow-1` class is applied, likewise for shrinking. 

* If only one flex-child of many has a `.flex-grow-1` class, that child will grow.
* If all flex-child elements have a `.flex-grow-1` class, they will all grow equally.
* If one flex-child element has a `.flex-grow-6` class while the rest have `.flex-grow-1`, that child will grow at six times the rate of the other child elements.

All of these same rules apply for shrinking. And, as above, the four size names can be concatenated:

```
.flex-shrink-2
.flex-small-grow-1
.flex-xlarge-shrink-6
```

The maximum value for grow or shrink is 6 and the minimum is 1.

<br>

___

<br>
#Utility


###Float:
`.flex-float-left` - float a flex-child element to the left

`.flex-float-right` - float a flex-child element to the right

The four name sizes can be concatenated:

```
.flex-small-float-left
.flex-large-float-right
```

<br>

###Other:
`.flex-center` - same as `margin: 0 auto;`

`.flex-no-wrap` - set on flex-parent to prevent flex-child elements from wrapping to next line

The four name sizes can be concatenated:

```
.flex-small-center
.flex-large-no-wrap
```