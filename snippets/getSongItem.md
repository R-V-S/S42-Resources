So this function is step 2 of getting the element with the class `song-item-number`. 

The element it takes as an argument is the element that was clicked on. 

Then, this function is going to use `getParentByClassName()` to get that element if the element with the class `song-item-number` is a parent of the element that was clicked on (e.g. if the user clicked on the play or pause button). 

If, on the other hand, the user clicked on the song row itself (the `<tr>` element), then the element with the class `song-item-number` is going to be a child of the element that was clicked on, so we can use a built-in JS function to find that element (like `element.querySelector()`). 

It's all about getting the song number, which we've stored as an attribute on the element with the class `song-item-number`. You don't _have_ to use a switch statement, but that's the solution the curriculum uses.