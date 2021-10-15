<h1 style = "text-align: center; background-color:black; color:white;">~ Q<small>&</small>A ~</h1>

## `>> Javascript week 3`

### Exercise

Source: [Codewars](https://www.codewars.com/)

Jaden Smith, the son of Will Smith, is the star of films such as The Karate Kid (2010) and After Earth (2013). Jaden is also known for some of his philosophy that he delivers via Twitter. When writing on Twitter, he is known for almost always capitalizing every word. For simplicity, you'll have to capitalize each word, check out how contractions are expected to be in the example below.

Your task is to convert strings to how they would be written by Jaden Smith. The strings are actual quotes from Jaden Smith, but they are not capitalized in the same way he originally typed them.

Example:

```
Not Jaden-Cased: "How can mirrors be real if our eyes aren't real"
Jaden-Cased:     "How Can Mirrors Be Real If Our Eyes Aren't Real"
```

My code:

```Javascript
String.prototype.toJadenCase = function () {

  // Check for invalid strings
   if(this === null || this === undefined || this === "") {
    return "";
  }

  // Capitalize first letter
  let capitalStr = this.charAt(0).toUpperCase();
  let char = "";

  // Loop through the string and capitalize all letters
  // following a space
  for (let i = 1; i < this.length; i++) {

    if(this.charAt(i-1) === " " && this.charAt(i) !== " "){
      char = this.charAt(i).toUpperCase();
    } else {
       char = this.charAt(i);
    }

    capitalStr += char;
  }
  return capitalStr;
};
```

Run code [here](https://jsfiddle.net/Halfdan/g1mdk803/7/)

Remarks:

- Initially I didn't realize that I had to use `this` and instead I declared a `str` argument for the function. This resulted in getting `undefined` errors from tests. After somebody pointed out I was writing a prototype function (duh!), I realized my mistake.

- There are more elegant solutions that use the `map()` and `slice()` functions.

## `>> Javascript week 1`

### Questions

#### Scope

- Difference between namespace and scope?
- What scope pitfalls in javascript should we be aware of?

#### this

- **this** is context dependant, can you clarify and mention the biggest pitfalls?
- Why doesn’t a class constructor have direct access to class methods, instead we have to use **this**:

```javascript
class User() {
  constructor() {
    this.method();
  }

  method() {}
}
```

#### Class

- What advantages do classes have over closures / constructor functions?
- Static functions of classes work on the class themself. Does **User** in User.method() still call the class constructor or are we just accessing an internal function (method) of another function object (User)?
- Why cant I declare a variable inside a class but outside its constructor:

```javascript
class User() {
 let cake = 'lie';

constructor() {}
}
```

- Is it only possible to create a global class variable (non accessible from outside the class) by using **#private**?

- How do the two following examples differ:

```javascript
class User() {
name = "John"
}
```

```javascript
class User() {
  constructor(){
  this.name = 'John';
  }
}
```

#### Prototype

- ~~Javascript is said to be a prototype based language, so what is the difference between Object.prototype, [[Prototype]] and \_\_proto\_\_?~~
