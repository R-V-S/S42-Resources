### Goal

We want the user to be able to click anywhere on the song row to play the song.

### Problem

To play the song, we need the code to figure out what the song number is. We're storing the song number as an attribute on the table cell with the class "song-item-number"... but unfortunately, the row is comprised of a bunch of elements, so we don't know which one they'll click on.

If they click on the table cell with the class "song-item-number", then getting the song number is cake. It's just a matter of getting the value of the "data-song-number" attribute.

But if they click on something else, how do we get the song number?

### Solution

The easiest way to get the song number if we don't know what element they're clicking on is to find the table row element itself – the parent of all of the table cells on that row. Then, from the parent, it's easy to target the child element that we want (.song-item-number).

The user could click on the parent directly or any one of its child table cells. Or they could click on the play button, which is an `<a>` tag with a `<span>` tag inside of it.

So how do we find the parent?

What we need to do is write a function that will take two arguments: a clicked element and a target element. It will then:

1. Check if the element that was clicked on is the element we're looking for. If not, then it will
2. See if it has a parent element. If it does, then it will 
3. See if that parent element is the element we're looking for. If not, then it goes back to step 2 and just keeps on repeating until it's either found the element we're looking for, or climbed to the top of the document (which will happen when the parent of the current element is null).
