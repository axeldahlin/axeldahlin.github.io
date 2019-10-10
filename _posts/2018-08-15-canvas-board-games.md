---
layout: post
title:  "Two-dimensional array + canvas = board games!"
date:   2018-08-15 20:01:19 +0100
categories: ["javascript", "canvas"]

---
This article will explain how to set up a grid that can be used for chess, a battleship game or any other board game.​

Personally, I struggled to understand the nested loop that is needed for this to work. By creating a much smaller version of the grid I finally understood the concept.

Here is what I did:

I created a canvas element in my HTML document.
```
<canvas></canvas>
```
In my canvas.js document I created the two-dimensional array.

It's an array that stores other arrays. In this example we have an array that stores three arrays, each of which stores three items. We will use this to model our 3x3 grid.

Then I selected the canvas element and gave it a height and a width. I declared a variable for the length of the grid cells . Then I used the getContext() method to get ready to draw on the canvas.
```
const array2D = [
    ['R', 'Y', 'R'],
    ['Y', 'R', 'Y'],
    ['R', 'Y', 'R']
];

const canvas = document.querySelector('canvas);

canvas.width = 600;
canvas.height = 600;
const cellSide = 200;

var ctx = canvas.getContext('2d');
```
### The tricky part: nested loops
Now we need to iterate through every array in array2D.
```
for (let i = 0; i < array2D.length; i++) {

}
And for every array we are going to iterate through every of its items. We do that with one more loop inside the first one.

for (let i = 0; i < array2D.length; i++) {

    for (let j = 0; j < array2D[i].length; j++) {

    }
}
```
To test that everything is working correctly we can throw in a console.log. If we compare this to array2D we see that we are iterating through it correctly.

First we iterate through the first array from left to right. Then the second from left to right. And lastly the third from left to right.


```
console.log(array2D[i][j]);

// Should output:
// R
// Y
// R
// Y
// R
// Y
// R
// Y
// R
```
Its time to draw! It will be hard to grasp exactly what going on in the following code if you have not played around with canvas earlier. That's not necessary right now, but if you are interested in learning the basics of canvas this tutorial is great.
```
for (let i = 0; i < array2D.length; i++) {

    for (let j = 0; j < array2D[i].length; j++) {
        let x = j * cellSide;
        let y = i * cellSide;
        
        cellColor = '#e74c3c';

        ctx.beginPath();
        ctx.fillStyle = cellColor;
        ctx.fillRect(x, y, cellSide, cellSide);
  }
}
```

What important to know here is that that the x and y in ctx.fillRect(x, y, cellSide, cellSide) determines the coordinates of the upper left corner of the rectangle that is drawn. The two last parameters determines the width and height.

The key here is the variables we have set in our loops(i and j). We will use these variables to manipulate the x and y variables for every iteration, to create our grid.

The first loop will run from start to finish only one time. But he second loop will run from start to finish for every iteration of the first loop.

Iteration through the loops
Let's go through what's happening when we run our program.

First loop #1 is called.

It will call loop #2.

In the first iteration of loop #2 the cell will be drawn with the upper left corner at the coordinates x: 0, y: 0. In other words the upper left corner.
```
let x = j * cellSide;
let y = i * cellSide;

// j = 0
// i = 0
// so this evaluates to:

x = 0;
y = 0;
```

In the second iteration of loop #2 we draw another cell but with the coordinates x: 200, y: 0. That's because j = 1.

Since we are still on the first iteration of loop #1, i = 0.
```
let x = j * cellSide;
let y = i * cellSide;

// j = 1 
// i = 0
// so this evaluates to:

x = 200;
y = 0;
Next step is the third iteration of loop #2. Remember, it's still the first iteration in loop #1. This time the cell is drawn with the coordinates x: 400, y: 0.

let x = j * cellSide;
let y = i * cellSide;

// j = 2 
// i = 0
// so this evaluates to:

x = 400;
y = 0;
```
Now we have drawn the first row of cells modeled of the first array in array2D.

Loop #2 is now finished and we go back to loop #1.

Loop #1 starts its second iteration and calls loop #2 again.

This time variable i = 1. Because it's now the second iteration of loop #1.

So loop #2 will run like this:

First iteration:
```
let x = j * cellSide;
let y = i * cellSide;

// j = 0 
// i = 1
// so this evaluates to:

x = 0;
y = 200;
```
Second iteration:
```
let x = j * cellSide;
let y = i * cellSide;

// j = 1 
// i = 1
// so this evaluates to:

x = 200;
y = 200;
Third iteration:

let x = j * cellSide;
let y = i * cellSide;

// j = 2 
// i = 1
// so this evaluates to:

x = 400;
y = 200;
```
Now we have drawn two rows of cells.

When loop #2 is finished we return to loop #1 that calls loop a third and last time. Same thing will happen, but this time variable i = 2.

This means that that the third row will be drawn underneath the previous one.

We can summarize the process like this:

When variable i increases, so does the y value.

When variable j increases, so does the x value.

We have now have our grid! But wait a minute...



Since every cell is the same color it's not much of a grid. Lets fix that that with an if statement. If the value of the current item is equal to "Y" draw the cell yellow.
```
const array2D = [
    ['R', 'Y', 'R'],
    ['Y', 'R', 'Y'],
    ['R', 'Y', 'R']
];

const canvas = document.querySelector('canvas');

canvas.width = 600;
canvas.height = 600;
const cellSide = 200;


var ctx = canvas.getContext('2d');


for (let i = 0; i < array2D.length; i++) {

    for (let j = 0; j < array2D[i].length; j++) {
        let x = j * cellSide;
        let y = i * cellSide;
        
        cellColor = '#e74c3c';

        if (array2D[i][j] === 'Y') cellColor = '#f1c40f';

        ctx.beginPath();
        ctx.fillStyle = cellColor;
        ctx.fillRect(x, y, cellSide, cellSide);  
    }
}
```
The result:



[And here is the project I was originally working on.](https://axeldahlin.github.io/mars-rover/)

Until next time!