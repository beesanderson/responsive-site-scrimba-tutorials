# Notes

### Explanation for column picture slide
- He was originally going to have this layout but chose a different approach instead but kept the picture to illustrate the "widths" of the various columns depending on their size relative to the smallest column (i.e the first column) 
- if they were all the same size we could have four columns of equal size and spacing, but they aren't. Instead columns 1, 3, and 4 is "1 column width" and column 2 is "2 columns wide" while columns while column 3 is "3 columns wide" and so fourth. 
![columns sizing](/flex-box-howtos/project-pictures/column-width.png)

- So basically he's having the columns with the width of "one column" recieve the class of "col-1" and the columns with the width of two columns "col-2" and 3 columns wide of "col-3"
- Percentages are the best option


#### Will need to subtract 5% from each column to add more "space-between" 
```css
.col-1 {
    width: 20%;
}

.col-2 {
    width: 45%;
}

.col-3 {
    width: 70%;
}
```
instead of: 
```css
.col-1 {
    width: 25%;
}

.col-2 {
    width: 50%;
}

.col-3 {
    width: 75%;
}
```
- don't forget to add 
`justify-content: space-between;` to the `.columns` section as it is the parent element of the `.col` elements



## Justify-Content and Align-Items Helps: 

### justify-content: aligns child elements of parent element along the *X-AXIS* of parent element

### align-items: aligns child elements of parent element along the *Y-AXIS* of the parent element 

![container example](/helpful-images/justify-content-align-items-helps/layout-ex.png)

- Blue container === parent of columns container
- magenta on the columns 

- by default align items will be stretch on any `display: flex;` parent element. The height of the parent element defaults the the height of the child with the "longest" or "most" content, in this examples case the middle column. 
- justify content = "main axis" or the horizontal axis
- align items = "vertical axis" or the "cross axis" 
- you can invert these two but this is default. 
![align items to flex start example](/helpful-images/justify-content-align-items-helps/align-items-flexstart.png)
- if you align the items to the "flex start" this is what you will get, that each individual column's content will have the box adjust to fit its own content 
