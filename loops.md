# Loops

### For loop
There are two ways to write a for loop.

#### The first:

```javascript
for(var i = 0; i < 10; i++){
  console.log(i)
}
```
The first part is the keyword `for`.
Followed by 3 parts `;` separated in parentheses.
- The first part instantiates the iteratee. Essentially gives you access to this value in your code block as i. It starts at 0 in this case.
- The second part is the comparison expression. That means this code will continue to execute until this expression evaluates to false.
- The third and final part is how much the iteratee is incremented after each execution of the loop

#### The second:

```javascript
// instantiate an array of names
var names = ["tyler", "nayana", "andy", "adrian", "nick", "jesse", "james"]
for(i in names){
  console.log(names[i])
}
```

- Again this for loop starts with the keyword `for`.
- In parentheses contains the iteratee followed by the keyword `in` followed by the complex data type you would like to iterate over(array or object)
- In the brackets contains the code you would like executed for each iteration of the loop

### You Do - Write a for loop that prints odd numbers to 100. Do not use conditionals

### While Loop(15m)
```javascript
var i = 0;
while(i < 10){
  console.log(i)
  // don't increment at first
}
```
#### ST-WG
What are the differences between `for` and `while`?
