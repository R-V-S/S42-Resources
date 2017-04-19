Inline block elements have a `vertical-align` value of `baseline`. 

This is good to know when using `display: inline-block` to horizontally stacked elements – especially if those elements are of different heights. If you want the blocks to align to the top of their container (usually the desired effect), you'll want to set `vertical-align` to `top`. Otherwise, with the default `baseline` value, the vertical positioning of the elements might seem very odd... 

Here's an example: https://codepen.io/R-V-S/pen/oYvxqV