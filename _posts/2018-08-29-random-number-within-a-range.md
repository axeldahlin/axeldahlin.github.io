---
layout: post
title:  "Random number within a range"
date:   2018-08-29 20:01:19 +0100
categories: ["javascript"]
permalink: /:categories/:title
---
A random number is necessary in many simple applications. And a random number within a range even more useful.

Objective: Generate a whole random number between 5 (inclusive) and 8 (inclusive). In other words we want to create a random variation of: ```5  6  7  8 ```

Lets start from the beginning. Lets write some code that will generate a  real number  (not a whole number) between 0 (inclusive) and 8 (exclusive):
```
Math.random() * 8
```
Since we want a whole number and not a real number lets wrap this in a Math.floor() like this:
```
Math.floor( Math.random() * 8 )
```
Now we are only generating whole numbers. Great! But the the numbers a still between 0 (inclusive) and 8 (exclusive). In other words: ```0 1  2  3  4  5  6  7 ```

Luckily the fix is easy. Lets just add the number 1.
```
Math.floor( Math.random() * (8 + 1) )
```
The result: ```0 1  2  3  4  5  6  7  8 ```

We are not quite home yet. Lets write:
```
Math.floor( Math.random() * (  (8 + 1) - 5) )
```
This is the same as: Math.floor( Math.random() * 4 )
And evaluates to a random variation of the numbers: ```0 1  2  3```

That is still not the answer.  We want a number between 5 (inclusive) and 8 (inclusive). So here is the final trick:
```
Math.floor( Math.random() * ( (8 + 1) - 5) ) + 5
```
The result is a random variation of: ```5  6  7  8 ```

Success! We basically just bumped up the whole range of possible numbers with 5. Here is how it is written with variables:
```
Math.floor(Math.random() * ((max + 1) - min)) + min
```

And here it is in a function:
```
function getRandomBetween(min, max) {
  return Math.floor(Math.random() * ((max + 1) - min)) + min;
}

console.log(getRandomBetween(5,8));
```
Thanks for visiting :)