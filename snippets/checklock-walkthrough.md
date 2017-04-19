# Checklock Exercise Walkthrough

**Start with something empty.** The first sentence of the exercise is _"Write a function named checkLock"_. so I'll do that first:

```
function checkLock() { }
```

How to create an empty function is a good [code snippet](https://en.wikipedia.org/wiki/Snippet_(programming)) to memorize.

Next, **iterate the requirements** for the function one by one and update the function. First, it says the function should _"have four arguments that are all numbers"_. So all I do there is I add 4 arguments to the function:

```
function checkLock(a,b,c,d) {

}
```

Those aren't very good argument names, but I don't want to get stuck on giving them perfect names, and I can always change them later.

Next, it says to _"return "correct" if the four numbers are a valid combination"_. OK. So I add a return statement to my function:

```
function checkLock(a,b,c,d) {
  return "correct";
}
```

Then it says to _"return "incorrect" if the four numbers aren’t a valid combination"_. OK, so now I add another return statement:

```
function checkLock(a,b,c,d) {
  return "correct";
  return "incorrect";
}
```

And now we have make the code smart, so that it executes the right return statement. The next line in the instructions is _"A combination is valid if"_ ... and because they used the word "if", I know I need an if/else statement. I leave the condition empty for now, but I split up the return statements, because I know that's the whole point of the if/else:

```
function checkLock(a,b,c,d) {
  if () {
    return "correct";  
  } else {
    return "incorrect";
  }
}
```

Then it says that the first number should be _"a 3, 5, or 7"_, so I add that to my if statement:

```
function checkLock(a,b,c,d) {
  if (a === 3 || a === 5 || a === 7) {
    return "correct";  
  } else {
    return "incorrect";
  }
}
```

Now the first number works as expected. Next, it says the second number should be 2, so I add onto our if condition:

```
function checkLock(a,b,c,d) {
  if (a === 3 || a === 5 || a === 7 && b === 2 ) {
    return "correct";  
  } else {
    return "incorrect";
  }
}
```

Next, it says that _"the third number is between 5 and 100. 5 and 100 are both valid numbers"_. OK, into the conditional it goes:

```
function checkLock(a,b,c,d) {
  if (a === 3 || a === 5 || a === 7 && b === 2 && c >= 5 && c <= 100) {
    return "correct";  
  } else {
    return "incorrect";
  }
}
```

... but now we have our first snaffu. This doesn't work. If we run this code:

```
console.log( checkLock(3, 2, 0, 0) );
```

We'll see that it returns `true` when it should return `false`. Why? Well... to figure that out, we have to walk through our conditional statement:

```
a === 3 || a === 5 || a === 7 && b === 2 && c >= 5 && c <= 100
```

What's going on there? JS parses those comparative operators from left to right, one at a time, so, step-by-step, the conditional above becomes:

```
true || a === 5 || a === 7 && b === 2 && c >= 5 && c <= 100
```

```
true || false || a === 7 && b === 2 && c >= 5 && c <= 100
```

```
true || false || false && b === 2 && c >= 5 && c <= 100
```

We can remove the duplicate `false` values:

```
true || false && b === 2 && c >= 5 && c <= 100
```

Now, the `&&` operator is a "short-circuit" style operator, which means if the value on the left resolves to false, the value on the right doesn't even get looked at. So we can take out `b === 2`:

```
true || false && c >= 5 && c <= 100
```

And for the same reason, we can take out `c >= 5` and `c <= 100`:

```
true || false
```

And that's `true`. Basically, if any comparison that preceeds an `||` will cause the whole expression to evaluate to `true`. So what we need to do to prevent that from happening is group our operators together. It's a good idea to _group together any operators that are evaluating the same value_, so we should put parenthesis around our group of `a` operations and group of `c` operations. It might also help if we split our conditional into multiple lines, for readability. That gives us:

```
function checkLock(a,b,c,d) {
  if ( (a === 3 || a === 5 || a === 7)  && 
       (b === 2) && 
       (c >= 5 && c <= 100) 
     ) {
    return "correct";  
  } else {
    return "incorrect";
  }
}
```

Now all that's left is to add a condition for the fourth number, which should be _"less than 9 or greater than 20. 9 and 20 are both invalid numbers"_:

```
function checkLock(a,b,c,d) {
  if ( (a === 3 || a === 5 || a === 7)  && 
       (b === 2) && 
       (c >= 5 && c <= 100) &&
       (d < 9 || d > 20)
      ) {
    return "correct";  
  } else {
    return "incorrect";
  }
}
```