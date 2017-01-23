# LEARNING OBJECTIVES

- Describe the role Javascript plays alongside HTML and CSS.
- List and describe the primitive data types.
- Describe uses of mathematical operators in Javascript.
- Define type coercion.
- Define and use complex data types.
- Explain the difference between `prompt` and `console.log`
- Practice proper JS syntax and semantic variable naming.
- Differentiate between true & false && truthy & falsey
- Describe why control flow is utilized in computer programming
- Write an if, else if, and else statement in JS
- Write a for loop and while loop in JS and differentiate between them
- Utilize loops to iterate through complex data types

## Framing
We've dabbled with HTML and CSS. There's a bit of interactivity we can program through CSS but not nearly enough! How can we start to add logic and behaviors to our web apps? .. Enter javascript.

# HTML, CSS and Javascript (20/20)

HTML, CSS and Javascript are technologies are the basic components of front-end development. Front-end frameworks and libraries that add "layers of abstraction" (the ability to do more with less code) make use of these three technologies.


#### If a web application or website were a building:

- ##### HTML: Structure and Content
 HTML would be like the most stripped down version of that building, just the structure of the building and some content.

- ##### CSS: Styling
CSS is responsible for the appearance of the building, adding granite floors, polished doors, wooden railings, etc. CSS styles the content of a website to look like more than just black text on a white background.

- ##### Javascript: Behavior and Functionality
Javascript might be like the building's elevator systems, ID-scanning & entry systems. Javascript handles interactivity and data.


## Think-Pair-Share: Identify Javascript features in Cookie Clicker.
* 2 minutes: Go look at [Cookie Clicker](http://orteil.dashnet.org/cookieclicker/) . Play with it. Think about what's allowing these behaviors to exist.
* 3 minutes: Discuss and compare findings in pairs.
* Think about what functionality the site has after it has loaded.
* Why would you say a particular feature is "run" by Javascript instead of, say, CSS?

### Findings
- #### Interactivity
  - Javascript defines behavior on a webpage, what happens you interact with it.
  - Data changes in response to user actions
    - Like: increment Like counter.
    - Comment: submit comment, appended to post.
- #### No Refreshes / User Experience (or UX)
  - When I click a cookie, CC is able to increment and update the counter on the page without a hard refresh.
  - When I comment on a post, Facebook is able to process my new comment and render it on the page without refreshing the entire page.
    - Gives the page a much smoother user experience compared to a static page that doesn't have this sort of functionality.
    - Imagine if Cookie Clicker just had an infinite number of static pages, one page for each quantity of cookies (html for 1 cookie, for 2 cookies, for 3 cookies, ... ∞ cookies...)
      - This would be terrible
- #### Communication with Servers
  - Javascript is somehow telling a server:
    0. That a user has taken a particular action (clicked a cookie, submitted a form, posted a post)
    0. To store some data associated with that interaction with the webpage
    (cookie quantity, form data, contents of a post)
    0. To display the results of that user-website interaction (updated cookie quantity, new user account log-in, new post on everyone's feed)

This is not an exhaustive list of Javascript properties, but we'll go over these and more in more detail later on in the course.

So, to sum up the main three components of front-end web development up in one word each...
- HTML: Structure
- CSS: Styling
- Javascript: Behavior

# JS: The Client-Side Programming Language of the Web (5/25)

- Brief history: Created in 10 days by [Brendan Eich](https://en.wikipedia.org/wiki/Brendan_Eich), of Mozilla. *Not* related to Java in any way but its name.
  - "Java" is to "Javascript" as "ham" is to "hamster"

- ST-wg: What's a programming language?
  - What can it do that a markup language like HTML can't?
  - It let's us do things! It lets us act on information, manipulate it, display it, pretty much whatever we want.
- Javascript enables us to do all that in a browser.
  - Using the tools you learned in the pre-work (e.g., data types, loops, functions).

## Why is it the dominant programming language of the web?
- Barriers to entry for learning Javascript are very low.
  - No additional software required to run it. Just a text editor and a browser.
    - You can even run it directly in the browser via its Javascript console.
      - Ex. Hide images on the GA website.
      - You'll learn more about the browser Javascript console when you start adding Javascript to the websites you make in this class.
- On top of that, it's supported by all web browsers.
- Javascript has evolved since its creation.
  - One of the biggest additions to JS was AJAX, which allows use to reload parts of a page without refreshing the entire thing (just like on Facebook). Big implications for User Experience.
- A lot of frameworks and libraries -- like Backbone and jQuery -- have emerged that enable us to do so much more -- and do it quickly -- with Javascript.

# Setting up our environment (5/30)

## First, create your HTML and JS

- `index.html` and `script.js`

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Yo</title>
  </head>
  <body>
  <script src="script.js"></script>
  </body>
</html>
```
You can also put your script tag in the head. Putting the tag in the body ensures that the rest of the page loads before your script files run. However, [HTML5 has two new attributes ](http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html) that allow for more control in how scripts run, regardless of whether they're place in the head or body.

## Next, open the site in Chrome, and open the Dev Tools

- Command + Option + I
- The "Console" is a REPL
  - “Read-Eval-Print Loop”.
  - Programming environment that lets us run Javascript code one line at a time.
  - What does it do?
    1. (R)eads our code.
    2. (E)valuates it.
    3. (P)rints it to the console.
    4. Then it (L)oops back to the beginning, ready to (R)ead the next line of code we feed it.
  - Primarily used for testing and debugging.

> `⌘ + ⌥ + i` enters you in the the chrome dev tools(if you're using chrome...) Here you can do a bunch of stuff like inspect elements and look at the html. More importantly for this class though, is it allows you to access the console which interacts with the JS you loaded to your page. In our case we'll see that interaction with the code below

In your `script.js` file add the following:
```js
console.log("hello world")
```

> console.log() is just a way to log something in  our REPL.  

## You do: [Data Types & Data Collections](https://github.com/ga-wdi-exercises/js-data-types/blob/master/exercise.md)(20 mins)

Reference [Data Types And Collections](./data-types-and-collections.md) to complete the above exercise.

## You do: [Booleans and Conditionals](https://github.com/ga-wdi-exercises/js-data-types/blob/master/exercise.md)(15 mins)

Reference [Booleans and Conditionals](./booleans-and-conditionals.md) to complete the above exercise.

## You do: [Loops and Fizzbuzz](https://github.com/ga-wdi-exercises/js-data-types/blob/master/exercise.md)(15 mins)

Reference [Loops](./loops.md) to complete the above exercise.

# BREAK (10min)

# Prompt

We've learned alot about basic data types, but it'd be nice if we had a way of getting user input into our browser! We'll learn some ways to use forms and such later in the course, but for now, we'll be getting user input using the `prompt()` function.

At any point in our JS code, if we write `prompt()`, a pop up box will open in our browser for a user to enter in text.

```js
// prompts user and stores value in the variable
var valueOfPrompt = prompt()
// logs value stored
console.log(valueOfPrompt)
```

You can also pass in a string as an argument to have the pop up box contain that string as a ... prompt.

```js
var age = prompt("How old are you?")
```

## We Do: Pseudocode Temp Converter Part I

Temperature conversion (Part I): [Temp Converter](https://github.com/ga-wdi-exercises/temperature_converter)

Review

## We Do: Pseudocode Temp Converter Part II

Temperature conversion (Part II): [Temp Converter](https://github.com/ga-wdi-exercises/temperature_converter)

Review

### Additional Exercises

- [Luhn Algorithm](https://github.com/ga-wdi-exercises/luhn_algorithm#challenge-validating-credit-card-numbers)
- [Anagram Detector](https://github.com/ga-wdi-exercises/anagrammer#anagram-detector)

# Syntax & Semantic Naming

## Syntax (5/65)

Variable syntax
- Should be named using camelCase lettering.
  - First letter of first word lowercase. First letter of remaining words uppercase.
  - No spaces or punctuation between words.

  ```javascript
  // camelCase
  var pizzaTopping = "pepperoni";
  ```
Semicolons
- General practice is to end every line with a semi-colon.
- Usage depends on the developer.

Comments
- Q: Why would you use comments?
  - Talked about this in the HTML class. Same reasoning applies.
- Types of comments
  ```javascript
  // Single line

  /*
    Multiple
    line
    comments
  */
  ```

- Use to explain the purpose or reasoning behind a piece of code.
- Help out other developers and future you.
  - If anything, it will help us out when grading your projects!


### Homework
- [Choose your own adventure](https://github.com/ga-wdi-exercises/choose_your_own_adventure_js)

# Review Questions
1. When would you use an array over an object? And vice-versa?
- What is the difference between `undefined` and `null`?
- Provide an example of a semantically-named variable. Explain your choice.
- What role does Javascript play on a website?
- What are the five primitive data types?
- What are the two composite data types? When would you use each?
- What is an example of type coercion?
