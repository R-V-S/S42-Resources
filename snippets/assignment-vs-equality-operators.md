Although they look almost exactly the same, the `=` operator is the [assignment operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment_Operators) – it assigns a value to a variable.

The `==` and `===` operators, on the other hand, are [comparison operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators) – they compare the expression on the left to the expression on the right and test for **equality**. They evaluate to `true` or `false`.

##The difference between `==` and `===`

The `==` operator is the **equality operator**. It compares two expressions, and it tries really hard to do it. If the two expressions are of different data types (e.g. if one is a number and the other is a string, like `5 == "5"`) then it tries to _"coerce"_ them to the same data type and then compare them. `5 == "5"` would evaluate to `true`.

The `===` operator is the **strict equality operator**. It compares two expressions, but unlike the standard equality operator, it's not very forgiving. Both expressions must be the same data type. If the two expressions are of different data types, then it automatically returns `false`. `5 === "5"` would evaluate to `false`.

Hope this clarifies things (if not, check out the included links for more explanations and examples).