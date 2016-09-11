# Booleans and Conditionals

## Booleans

Two values: `true`, `false`.  To be clear, these are not strings, but the concepts of true and false.

Oftentimes you'll be producing boolean values when comparing two values
- Comparison operators: `==`, `===`, `<`, `>`, `<=`, `>=`

```javascript
1 === 1
=> true

1 === 2
=> false

1 == "1"
=> true
```

> What is the differences between the last two? When using `===`, it checks for both the data type and value. `==` only checks for value. Under the hood, though, `==` converts the data type to the same data type and then executes comparison.

## true vs false (5/115)
So we all know the boolean values of `true` and `false` But there is also a concept of "truthy" and "falsey" In Javascript, the following things are "falsey":
- false
- 0 (zero)
- "" (empty string)
- null
- undefined
- NaN (a special Number value meaning- Not-a-Number!)

> Everything else is "truthy". Why might we need this programmatic concept of "truthy" and "falsey"?(ST-WG)

## Comparison Operators (5/120)

- `&&`
- `||`
- `!`

What do the following evaluate too? (ST-WG)

```js
true && false
true || false
5 > 12 && 12 >= 12
17 > 12 || 4 <= 4
```

Let's check out comparison operators in node. node is a server side Javascript environment. We'll talk more about it later in the course.

- `<`, `<=`
- `>`, `>=`
- `!=`, `!==`
- `==`, `===`

```javascript
55 == "55"
=> true
55 === "55"
=> false
```

## Conditionals (15/135)

Let' talk through the following code (10m)

```javascript
var age = 24;
if(age < 18) {
  console.log("You're too young to enter this club! Get outta here")
}
else if(age >= 18 && age < 21){
  console.log("Come on in! But no Drinking!!")
}
else{
  console.log("Come on in!")
}
```

Conditionals will always follow this pattern. There is a key word(if, else if, else). Followed by an expression that will evaluate to true or false in parentheses. Then followed by code to execute when condition is met.

## Whitelisting vs Blacklisting
What's wrong with the following code?:

```javascript
var age = 24;
if(age > 21){
  console.log("Come on in!")
}
else if(age > 75){
  console.log("Come on in, but I don't know if this is the place for you!")
}
else{
  console.log("get outta here youngin!")
}
```
