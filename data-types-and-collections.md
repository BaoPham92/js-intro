# Data Types and Collections

Primitive data types are the building blocks of Javascript.
- Whenever you do anything in Javascript, you are creating and changing these basic pieces of information.

There are five primitive data types.

### ST-wg: What are they?

  1. Numbers
  2. Strings
  3. Booleans
  4. Undefined
  5. Null

We store data types in variables. A variable is a "bucket" that holds data. You can pass the bucket around, empty it, refill it, etc.

- Format: `var NAME = DATA;`

  ```javascript
  // For example...
  var myClass = "WDI13";

  // After declaration you can then reference variables by just their name, without "var".
  myClass;
  => "WDI13"
  ```

- Javascript is a "dynamic" or "untyped" language, meaning a variable can switch between data types.

  ```javascript
  // This change is valid in Javascript.
  var myFavoriteNumber = 5;
  var myFavoriteNumber = "five";
  ```
## Operations

- Math in Javascript follows the same rules you've known since elementary school math.
- Basic operators: `+, -, *, /`

  ```javascript
  // Addition
  10 + 2;
  => 12

  // Subtraction
  10 - 2;
  => 8

  // Multiplication
  10 * 2;
  => 20

  // Division
  10 / 2;
  => 5
  ```

- Order of Operations: PEMDAS or **P**lease **E**xcuse **M**y **D**ear **A**unt **S**ally (Parenthetical expressions, Exponentiation, Multiplication, Division, Addition, Subtraction)

  ```javascript
  // This would be interpreted as...
  // Go through step by step with class.
  ( 4 + 2 ) * ( 12 / 3 );
  => 6 * 4
  => 24

  // How would this be interpreted?
  // Like operators are processed from left-to-right. In this case, division happens before multiplication.
  ( 8 / 4 * 2 ) + 1
  => ( 2 * 2 ) + 1
  => 5
  ```

- % (Modulus)
  - Returns the remainder of a division operation.

    ```javascript
    // What is the remainder of 12 / 5?
    12 % 5;
    => 2
    ```

  - Q: Modulus has a pretty handy use case: to check if a number is even.
    - A number is even if it is divisible by 2.
    - Check if a number is even: `NUMBER % 2`
      - What should this return?

      ```javascript
      // Returns 0 if even.
      4 % 2;
      => 0

      // Returns 1 if odd.
      5 % 2;
      => 1
      ```

### NaN ("Not a number")
- A special number...that's not a number?

    ```javascript
    typeof NaN
    => "number"
    ```

  - You usually get NaN when the result of a math operation is not real (e.g., dividing 0 by 0, multiplying strings together).

    ```javascript
    0/0;
    => NaN
    ```

- You can test whether a value is a valid number using the `isNaN()` function.

```javascript
// isNaN returns false if used on a valid number.
var myFavoriteNumber = 5;
isNaN( myFavoriteNumber );
=> false
```

## Undefined & Null

Values that indicate the lack of a meaningful value.
- Anybody else find that weird? How is there more than one data type for nothing?
- Q: What's the difference?

Undefined: automatically applied to a variable with no value.

```javascript
// A primitive data type of type undefined with only one value: "undefined".
typeof undefined;
=> "undefined"

// Any property that has not been assigned a value is "undefined".
var nothing;
=> undefined

// A function with no defined return value has a return value of "undefined".

// You won't find yourself assigning "undefined" to a value. That's where "null" comes in.
var nothing = undefined;
```

Null: an explicitly-assigned non-value.
  - Javascript will never set anything to `null` by itself. `null` only appears when you tell it to.
  - If I'm not mistaken, the only thing that's inherently `null` in Javascript is `null` itself!
  - Can you imagine a situation where that would be useful?
    - Placeholder for a variable that you know will be replaced with an actual value later on.

So the main difference between `undefined` and `null` is intention. Other than that, they're both...nothing.

### Type Coercion

Javascript will try to make sense of any strange operations you throw at it.
- By "strange", I mean subtracting a number from a string, or multiplying `null` by 100.
- It does this through something called "type coercion" -- converting data types.

You might encounter this when dealing with numerical values but for whatever reason some of them are in string form.

```javascript
// In some cases Javascript is helpful and converts strings to numbers in the correct way.
"3" - "2"
=> 1

// ...but sometimes it doesn't. In this example, the + operator acts as if it's concatenating two strings.
"3" + "2"
=> 32

// And this?
"five" * 5;
=> NaN
```

When in doubt, convert data types that should be numbers using `parseInt()`.

```javascript
// parseInt converts a string to a number value, if available.
parseInt( "3" );
=> 3

parseInt( "burrito" );
=> NaN
```

There are other examples of type coercion, but the point here isn't to remember them all. Just be aware that sometimes Javascript will fire weird results back at you with no explanation. Sometimes, type coercion might be the culprit.

## Strings

Strings are words in javascript!

We instantiate strings using the "string literal" form.

```javascript
// Can use single quotes to instantiate a string...
var greeting = 'Hello!';

/// ...or double quotes.
var greeting = "Hi there!";
```

### Escape sequences

- Sometimes you will need to use special characters or formatting in strings that can't be entered the same way as you would in a word processor. In these cases, you use "escape sequences".
- Syntax: backslash + letter (e.g., `"\n"`).
- Examples:

  ```javascript
  // "\n" = new line
  "Hello\nGoodbye"
  =>"Hello"
  =>"Goodbye"

  // "\t" = tab
  "\tOnce upon a time..."
  => "     Once upon a time..."
  ```

- You can check out more escape sequence examples [here](http://www.javascriptkit.com/jsref/escapesequence.shtml).  

### Concatenation

- Like numbers, you can add strings together using `+`.

  ```javascript
  var city = "Washington, ";
  var state = "DC";
  var address = city + state;
  => "Washington, DC"
  ```

- You can't, however, use other math operators on strings.

  ```javascript
  // Q: What do you think happens when we try to subtract strings from each other?
  // When using the "-" operator, the operands are treated as numbers.
  "hamburger" - "ham"
  => NaN

  // The same goes for multiplication and division.
  "hamburger" * 3
  => NaN
  ```

String methods
- Javascript comes with methods you can use to inspect and modify strings.
- Examples:

  ```javascript
  // .search(): find the starting index of a string value.
  // String indexes are 0-based, so the index of a string's first character is 0.
  var greetings = "Hi there Nayana!";
  greetings.search( "Nayana" );
  => 9

  // .slice(): return and store a portion of a string.
  var greetings = "Hi there Nayana!";
  var buddy = greetings.slice( 9, 15 );
  => "Nayana"
  ```

- More examples [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

## Composite Data Types

Composite data types are collections that allow us to store multiple data types.
- There are two kinds in Javascript. What are they?

## Arrays
- Ordered collection of related data types.
- Organized by index.
  - Indexing begins at 0 (e.g., first element in an array has an index of 0, the second has an index of 1, and so on).

There are two ways to instantiate an array...  

```javascript
// Instantiate with an array literal.
var mountRushmore = [ "Washington", "Jefferson", "Roosevelt" ];

// Can also instantiate using the Array constructor. Constructors are like regular functions used with the "new" keyword. Useful for creating similar objects.
var mountRushmore = new Array( "Washington", "Jefferson", "Roosevelt" );

// Be careful when using the Array constructor. If you feed it a single numerical value, it will create an empty array of that length.
var numbers = new Array( 5 );
=> [ , , , , ]

// ...but if you feed it anything else, it will create a single-value array.
var animals = new Array( "dog" );
=> [ "dog" ]
```

Accessing array values...  

```javascript
// Indexing begins at 0.
// How do I access the first, second and third elements of the array?
mountRushmore[0];
=> "Washington"
mountRushmore[1];
=> "Jefferson"
mountRushmore[2];
=> "Roosevelt"

mountRushmore.push("Lincoln");

mountRushmore[3];
=> "Lincoln"

// You can also place arrays within arrays.
var letters = [ ["a","b","c"], ["d","e","f"], ["g","h","i"] ];

// How would I go about accessing the letter "f" in the above array? Walk me through it.
letters[1][2];
=> "f"
```

Array methods
- There are a lot of useful methods that come with Javascript we can use to inspect and modify arrays. To learn what some of them are...
  - `.length`
  - `.push`
  - `.indexOf`
  - `.reverse`

> There are many more, but these are the most widely-used.

- Documentation
  - [MDN Array Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
  - Navigating documentation is a great skill to have. Some sets of documentation are harder to navigate than others, but if you have a sense of how to dig through a massive trove of information like MDN or RubyDocs, you'll become a much more efficient programmer.
