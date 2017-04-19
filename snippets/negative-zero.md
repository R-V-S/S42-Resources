
# Why is `-0` possible in JavaScript? 

It's basically just an artifact of how floating point numbers are stored on the back-end. A JS number has 52 bits dedicated to the [significand/fraction/mantissa](https://en.wikipedia.org/wiki/Significand), 11 bits dedicated to the exponent, and 1 bit for the sign.  

Unless the number crosses the 0 boundary, the sign remains unchanged, allowing for `-0`.

There are a couple of ways of dealing with `-0`:

```
// Remove the sign from an integer
parseInt(-0); // evaluates to 0

// Remove the sign from -0 but preserve other floating point numbers:
num = num > -1 ? Math.abs(num) : num;

// Check for values that equal zero (i.e. +0 and -0) and replace them with zero explicity:
num = num === 0 ? 0 : num;

// Compare between 0 and -0
1/-0 === -Infinity; // evaluates to true
1/0 === -Infinity; // evaluates to false

```