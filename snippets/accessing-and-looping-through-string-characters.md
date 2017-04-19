
```js
// access elements of a string by index
console.log('hello'[0]); // returns 'h'

// convert a string to an array
Array.from('hello'); // returns ["h", "e", "l", "l", "o"]

// convert an array back to a string
['h','i'].join(''); // returns 'hi'

// loop through a string and grab its letters
var str = 'hello';
for (var i=0; i < str.length; i++) {
  console.log( str[i] );
}
```