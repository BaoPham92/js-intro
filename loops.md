# Loops

## `for` loop

<!-- AM: Add some intro text -->

```js
for(var i = 0; i < 10; i++){
  console.log(i)
}
```
The first part is the keyword `for`.
Followed by 3 parts `;` separated in parentheses.
- The first part instantiates the iteratee. Essentially gives you access to this value in your code block as i. It starts at 0 in this case.
- The second part is the comparison expression. That means this code will continue to execute until this expression evaluates to false.
- The third and final part is how much the iteratee is incremented after each execution of the loop

## `for in` loop

<!-- AM: Add some intro text -->

```js
var names = ["tyler", "nayana", "andy", "adrian", "nick", "jesse", "james"]
for(i in names){
  console.log(names[i])
}
```

- Also begins with the keyword `for`
- The parentheses contain the iteratee (the variable representing the index), followed by the keyword `in`, followed by the complex data type you would like to iterate over (either array or object)


### While Loop

<!-- AM: Needs some intro text -->
<!-- AM: Need to update example -->

```js
var i = 0;
while(i < 10){
  console.log(i)
}
```
