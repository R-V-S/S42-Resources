## Brackets

- Install Brackets from [the home page](http://brackets.io/)
- [Brackets How-To Guide](https://github.com/adobe/brackets/wiki/How-to-Use-Brackets): an overview of Brackets' many features.
- [Brackets Course](http://css-snippets.com/brackets-course/): video demonstrations on how to use Brackets.

## Code Wars

| Kata                                                                                               | Difficulty[*](#difficulty) | Hint                                                                                                           |
|:---------------------------------------------------------------------------------------------------|:---------------------------|:---------------------------------------------------------------------------------------------------------------|
| [A Needle in the Haystack](http://www.codewars.com/kata/a-needle-in-the-haystack/train/javascript) | 8                          | Arrays have a function that returns the location of an item, search the web to find it.                        |
| [The `if` Function](http://www.codewars.com/kata/the-if-function/train/javascript)                 | 8                          | To invoke a function, append parentheses (`()`) to its name.                                                      |
| [Vowel Remover](http://www.codewars.com/kata/vowel-remover/train/javascript)                       | 8                          | Strings have functions that return and replace the character at a given location, search the web to find them. |
| [Split the Bill](http://www.codewars.com/kata/split-the-bill/train/javascript)            | 7                          | Calculate the _average_ each person owes, then work your way from there. If you run into rounding problems, look up [how to round a number](https://www.google.com#q=javascript%20round%20to%202%20decimals) down to two decimal points. |
| [Is Undefined?](http://www.codewars.com/kata/is-undefined/train/javascript)               | 7                          | Go back and refresh your memory about the `typeof` operator.                                                                                                                                                                             |
| [Make it Lazy](http://www.codewars.com/kata/lazily-executing-a-function/train/javascript) | 7                          | Brush up on the local [`arguments` variable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments) available to every function, and take another look at `apply()`.                                     |

<a name="difficulty"></a>
\*<sub> Difficult problems have lower ratings.</sub>

<a name="bonus-challenge"></a>
## Bonus Challenge: [Stacked Deck](http://www.codewars.com/kata/stacked-deck-create-a-cheaters-deck-of-cards/train/javascript)

>This bonus challenge is optional, but we strongly encourage you to attempt it.

In this challenge, Bloc went all-in on a hand of poker. We had a flush, but Codecademy pulled a ringer and got a full-house. We owe them $3M by next Tuesday and if we don’t pay up, they’re going to tell everyone we smell.

We’re going to raise that money like a gambler… by gambling. To help us win, you will write a deck-shuffling algorithm. By default, your code must shuffle a deck as per usual: semi-randomly using a [pseudo-random number generator](http://www.w3schools.com/jsref/jsref_random.asp).

Here’s the fun: whenever we pass you a `cheatCode`, you should use that value to build a cheat deck. Whenever we pass you the same cheat code, you must return the same cheat deck each time. Here’s an example:

```js
var shuffledDeckOne = new StackedDeck();
shuffledDeckOne.shuffle();
var shuffledDeckTwo = new StackedDeck();
shuffledDeckTwo.shuffle();
var cheatDeckOne = new StackedDeck(1);
var cheatDeckTwo = new StackedDeck(1);
cheatDeckOne.shuffle();
cheatDeckTwo.shuffle();
```

`shuffledDeckOne` and `shuffledDeckTwo` are normal decks, shuffled randomly, and are _not_ identical. After shuffling `cheatDeckOne` and `cheatDeckTwo`, we expect both of these decks to have the exact same order of cards. We passed the same cheat code to both decks: `1`. Here's another caveat:

```js
var cheatDeckA = new StackedDeck(1);
var cheatDeckB = new StackedDeck(2);
var cheatDeckC = new StackedDeck(2);
```

In this example, `cheatDeckB` is identical to `cheatDeckC` but both of them are different than `cheatDeckA`. `cheatDeckA` is identical to `cheatDeckOne` and `cheatDeckTwo` from the previous example. Each cheat code corresponds to a unique deck.

Store the deck in an array:

```js
shuffledDeck = [];
```

Each deck must be complete with the full set of 52 unique cards, each represented by a string. For example, `"5c"` for the five of clubs, and `"Qs"` for the queen of spades. Here’s the full breakdown:

- **A** = Ace
- **K** = King
- **Q** = Queen
- **J** = Jack
- and **2** through **10** represent the numbered cards

Suits are lower-case letters:

- **d** = Diamonds
- **h** = Hearts
- **c** = Clubs
- and **s** = Spades

Your shuffling must be random enough that each call to `shuffle` generates a different deck unless we provide a cheat code. But please, do _not_ mess this up, Bloc is in deep on this one.