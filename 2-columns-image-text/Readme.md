## Problem Description

I have a container that will occupy 100% of its parent's width. I want `.container` to divide into two columns; `.left` occupying roughly `30%` and `.right` occupying `70%` of the `.container`'s width. Consequently I want the height of `.container` to be the height of its `.right`(the height of `.right`'s content) child. 

_Some complications_: 

* `.left` will contain an image of unknown dimensions and regardless of those dimensions, the width of `.left` should not exceed the 30% of its `.container`'s width nor should its height be larger than `.container`'s height. 

* A large image will increase `.left`'s height and therefore `.container`'s height (undesirable)

* The image should always occupy all the available space, keep its aspect-ratio and center both horizontally and vertically.

### Explanation of Solution

* `.container` will be as tall as its content. 

* `.container` is given `display: grid` and `grid-template-columns` with the desired fractions/percentages to form 2 columns;

* Ask `.left` not to be higher than the available space with `max-height: 100%`. The available space is the height resulting of the content of `.right` which is a title and a few paragraphs

* Ask `img` inside `.left` to be as wide and tall as its containing block (`.left`) a space with `width: 100%; height:100%;` 

* Ask `img` to cover all the available space while keeping its aspect-ratio with `object-fit: cover`

### Notes

* `.container` grid properties which sets the columns restrict the width of the blocks and therefore there is no worries the images will expand their containers width. 

* Another approach accomplishing the same results is given in [CSS - Expand float child DIV height to parent's height](https://stackoverflow.com/questions/4804581/css-expand-float-child-div-height-to-parents-height)
