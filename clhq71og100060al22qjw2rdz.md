---
title: "JavaScript var, let, const. Difference between var and let"
seoTitle: "Difference Between JavaScript's var, let, const: A Comprehensive Guide"
seoDescription: "Discover the difference between JavaScript's var, let, and const. Learn how to use these variables effectively and avoid common coding mistakes."
datePublished: Tue May 16 2023 11:31:41 GMT+0000 (Coordinated Universal Time)
cuid: clhq71og100060al22qjw2rdz
slug: javascript-var-let-const-difference-between-var-and-let
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1684226318510/768371c2-55c1-445d-9da1-d62ca8c0cbd3.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1684226336327/94d43b74-ef58-4ed4-bbd4-ef983bbbdb0e.png
tags: variables, programming, javascript, html, var-let-const

---

If you have ever written a single line of JavaScript(JS) code you must have encountered these 3 weird keywords, [var](https://www.w3schools.com/js/js_variables.asp), [let](https://www.w3schools.com/js/js_let.asp), and [const](https://www.w3schools.com/js/js_const.asp). It is simple and fairly easy to understand the difference between let and const. However, I have seen a lot of people who struggle to understand the difference between var and let. So while exploring all three our main focus of this article would be var vs let.

Before jumping into var, let, and const, do we know what variables are? We can simply put it like this, variables are some form of containers that are used for storing data. And in JS we can declare variables in 4 ways:

1. with **var**
    
2. with **let**
    
3. with **const**
    
4. with nothing
    

## var

We can simply declare any variable with the keyword **var**. For example:

```javascript
var name = "Riyadh";
var age = 22;
var email = "mahadihassanriyadh1@gmail.com";
```

**var** is the old way of declaring variables in JS. **let** and **const** were introduced to JS in 2015. Before that we only had **var**. So if we need our codes to run in older browsers we must use **var**.

### Variables Declared with var are Globally Accessible

Variables declared inside a block scope with var are globally accessible. As block scope was not available before ES6 (2015).

```javascript
{
    var age = 55;
}
console.log(age); // variable age is accecible outisde the block ✅


var name = "Riyadh";
{
    var name = "Mahadi";
}
// this will print Mahadi
console.log(name);
```

### Why let and const?

Previously, all variables were the same, they all could either stay the same or change. But now we have two different types of variables: **let** and **const**.

This is helpful because it prevents mistakes. For instance, let's say you declared a variable called **email** two years ago that stores a user's email address. Now you need to add another variable to store the admin's email address. If you use the same variable name **email** for both, you will overwrite the user's email with the admin's email.

Using "let" and "const" allows you to avoid this problem by making it clear which variables can change and which cannot. "Const" variables cannot be changed once they're declared, while "let" variables can be changed later on.

```javascript
// user email
var email = "mahadihassanriyadh1@gmail.com";

/*
....
1000 lines of code
....
*/

// admin email
var email = "admin@gmail.com";

// Oh, no! the user email has been replaced by admin's email
```

## let (let vs var)

As I have previously said the keyword **let** was introduced in ES6 (2015). There are a few concepts about **let** you need to understand before going into any JS-related coding interviews. Let's see the concepts one by one:

### Cannot be Redeclared

Certainly, it is not possible to accidentally redeclare a variable, initially declared with let. Whereas it is possible to redeclare a variable initially declared with var.

```javascript
// not possible ❌
let name = "Riyadh";
let name = 87;

// possible ✅
var email = "mahadihassanriyadh1@gmail.com";
var email = "admin@gmail.com";

var id = 98323; // possible ✅
let id = 12324; // not possible ❌

{
    let id = 12324; // possible ✅
    let id = 34234; // not possible ❌
}

let food = "Burger";
{
    let food = "Pizza"; // possible ✅
}
```

### Block Scope

Before ES6 (2015), JS did not have anything as Block Scope. It only had **Global Scope** and **Function Scope**.

```javascript
// Global Scope
let name = "Riyadh";
var age = 22;
{
    // name, age can be accessed from here ✅
}


// Function Scope
function sum(a, b) { 
    let total = a + b;
    return total;
}
// total can't be accessed from here ❌


// Block Scope
{
    let name = "Mahadi";
    var age = 18;
}
// name can't be accessed from here ❌ but age can be accessed ✅
```

Learn more about JS Scope from [here](https://www.w3schools.com/js/js_scope.asp).

### Hoisting

In JS, all declarations are hoisted. As a result, it is certainly possible to use a variable (declared with var) before it has been used. We can simply think of hoisting as lifting up the declarations at the top of the stack before parsing any code. To know more about JS hoisting you can visit [here](https://www.w3schools.com/js/js_hoisting.asp).

```javascript
// possible ✅
name = "Riyadh";
var name;

// not possible ❌
age = 22;
let age;
```

Now you may think that var declarations are hoisted, but let declarations are not. This is not the case, all the declarations in JS are hoisted. So how can we use a variable declared with var and cannot use a variable declared with let?

Both the variables declared with var and let are hoisted to the top of the block, however, variables declared with let are not initialized. That simply means the variables declared with var are hoisted to the top of the block, and initialized with a value as well. Yet, in the case of let the value is not initialized. This means the code block knows that it has a variable called **age**, nonetheless, it will not be able to use it until it has been declared. This will cause a `ReferenceError`. This variable remains in a temporary area where a variable is inaccessible until a value has been initialized, and this temporary area is known as a [temporal dead zone (TDZ)](https://www.freecodecamp.org/news/javascript-temporal-dead-zone-and-hoisting-explained/).

So, now if you get a question in your interview is let variables are hoisted or not, you can provide the right answer with confidence.

## const

All the properties of const are similar to let with a few differences.

### Values Cannot be Reassigned

The main difference is variables declared with let can be changed later on whereas we cannot change a variable declared with const.

```javascript
let age = 18;
age = 22; // reassign possible ✅
let age = 33; // redeclaration not possible ❌

const pi = 3.14159265359;
pi = 3.14; // reassign not possible ❌
```

### Must be Assigned at the Same Time as Initialization

We cannot initialize a variable first and then leave it for later to assign a value with const.

```javascript
// will give an error ❌
const pi;
pi = 3.14;
```

Thank you so much for reading till the end. You can connect with me through [LinkedIn](https://www.linkedin.com/in/mahadihassanriyadh/), [GitHub](https://github.com/mahadihassanriyadh), [Twitter](https://twitter.com/i_am_riyadh), and [Instagram](https://www.instagram.com/mahadihassanriyadh/).

The following resources have been used to write the blog:

1. [https://www.w3schools.com/js/default.asp](https://www.w3schools.com/js/default.asp)
    
2. [https://youtu.be/HS6nkKeuP\_M](https://youtu.be/HS6nkKeuP_M)
    
3. [https://www.freecodecamp.org/news/javascript-temporal-dead-zone-and-hoisting-explained/](https://www.freecodecamp.org/news/javascript-temporal-dead-zone-and-hoisting-explained/)