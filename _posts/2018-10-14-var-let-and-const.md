---
layout: post
title:  "Var, let and const... Let us sort them out!"
date:   2018-10-14 20:01:19 +0100
categories: ["javascipt"] 
permalink: /:categories/:title
---
The other day I was daydreaming about being interviewed for a web development position and something horrible happened. In the dream the recruiter asked me about the exact definition of var, let and const..

I knew that we do not use var any more and that const is used for values that can not be updated. But what is the exact differences between the three?

Do avoid these kind of horrible daydreams I will sort this out once in for all.

## var
* Scope: Function
* Can be re-declared: Yes
* Can be updated: Yes

Before ES6 var was the only variable player in the game. Var in function scoped. That means that if a var is declared inside a function it is only available inside that function. If a var is declared outside of any function it will have global scope. That means that it is available everywhere, in every function.  A  var can be both updated and re-declared. One problem with var is that because of this developers sometimes intended to create a new variable but unintentionally used the same variable name. These kind of situations lead to surprising outputs and buggy code.
```
var myVar = 'This is a var';

if (true) {
  var myVar = 'Here is some text';

}

console.log(myVar); // Logs: Here is some text
```
If you are aware of that you are re-declaring the var this is not a problem. But if you was not aware about this the output might surprise you or lead to bugs.

## let
* Scope: Block
* Can be re-declared: No
* Can be updated: Yes

Let is block scoped. That means that a let that if declared inside a pair of {} it is available only inside those curly brackets. That solves the scope problem that var had. With let we do not have to worry about two variables with the same name messing up our code. As long as they are declared within different scopes they are treated as different variables. And if you re-declare a let inside the same scope there will be en error.  A let can be updated like this:
```
let myLet = 'This is a let!';
myLet = 'Here is my updated let!';
But it can not be re-declared like this:

let myLet = 'This is a let!';
let myLet = 'Here is my updated let!';
```
## const
* Scope: Block
* Can be re-declared: No
* Can be updated: No

Const have block scope and can not be re-declared, just like let. But unlike let and as the name might forewarn a const can not be updated. Its value is constant. So that means that this will not work:
```
const myConst = "This is my constant const!"
const myConst = "I will try to update you!"
```
### The weird part: hoisting
There is one more thing that separates var from let and const.  Vars are hoisted. That means that they are moved to the top of the scoped and initialized with a value of undefined.
```
console.log(myVar)
var myVar = 'This is a var';
// Logs: undefined
```
This would not be the case with const and let. If we use a let or a const before they are declared it will result in a ReferenceError:
```
console.log(myLet)
let myLet = 'This is a let';
// ReferenceError: myLet is not defined
```
And that is it! No more day dreams about confusing var, let and const ever again.