---
layout: post
title:  "How to generate a radnom number?"
date:   2018-07-07 20:01:19 +0100
categories: ["javascript"] 

---
A random number can be useful every time your program to to something.... well,  random. Maybe you want to simulate a shuffled deck of cards, a dice roll or something other that doesn't so obviously depend on a random outcome.

### Math.random()

The core of randomness. This method generates a number between 0 and 1.

Never 0.

Never 1.

Always something in between with a lot of numbers after the decimal point.

If you console.log Math.random() three times you get something like this:

```
console.log(Math.random());

console.log(Math.random());

console.log(Math.random());

// possible output:

0.5685422154071946

0.4720088746581983

0.8466934249411713
```
This is not really what we are looking for.

### Math.random() * 10

Lets multiply Math.random() with the number 10. Now we get a random number between 0 and 10.

It will never be exactly 0 and never exactly 10.

```
console.log(Math.random() * 10);

console.log(Math.random() * 10);

console.log(Math.random() * 10);

// possible output:

8.5685422154071946

1.4720088746581983

6.8466934249411713
```
We are getting closer but we are not quite where we want to be yet. Lets get rid of these annoying numbers after the decimal point.

### Math.floor()

The solution is Math.floor(). It takes a real number and rounds it down to the closest integer.

Note: Numbers that are not whole numbers are called real numbers. Examples:
```
1.5

10.4566

0.0001
```

Lets combine Math.floor() and and Math.random() * 10 to get a random number between 0 and 9:
```
console.log( Math.floor( Math.random * 10 ) );

console.log( Math.floor( Math.random * 10 ) );

console.log( Math.floor( Math.random * 10 ) );

// possible output:

4

8

2
```
That is it! Randomize away!