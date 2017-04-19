# The Original FizzBuzz Challenge: The Moral of the Story

I believe that there's a simple idea that's being tested for with this challenge – one that even many seasoned coders don't spot. It's that "FizzBuzz" is divisible by "Fizz" and "Buzz" in much the same way that 15 is divisible by 3 and 5. 

With that in mind, you can **build** the output using two conditionals. The inside of the loop could then look something like this:

```
var output = '';
if (i % 3 === 0) { output += 'Fizz' }
if (i % 5 === 0) { output += 'Buzz' }
arr.push(output ? output : i);
```

Building output efficiently based on overlapping conditions is an extremely practical approach: It's a technique that can be used effectively in everday web development. That's why the FizzBuzz challenge became so popular in interviews. It's a litmus test for practical _and_ efficient problem solving.