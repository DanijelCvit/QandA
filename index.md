<h1 style = "text-align: center;background-color:black; color: white;">Q&A</h1>

## `Javascript week 1`

### Questions

- Difference between namespace and scope?
- What main scope pitfalls in javascript should we be aware of?
- this is context dependant, can you clarify and mention the biggest pitfalls?
- What advantage do classes have over closures/ Constructor functions?
- Why doesn’t a class constructor have direct access to class methods, instead we have to use this:

```javascript
class User {
  constructor() {
    this.method();
  }

  method() {}
}
```

- Static functions of classes work on the class themself. Does User in User.method() still call the class constructor or are we just accessing an internal function (method) of another function object (User)?
- Why cant I declare a variable inside a class but outside its constructor:

```javascript
class User() {
 let cake = 'lie';

constructor() {}
}
```

Is it only possible to create a global class variable (non accessible from outside the class) by using #private?

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
