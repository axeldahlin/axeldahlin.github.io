---
layout: post
title:  "What you don't know about arrays"
date:   2018-07-14 20:01:19 +0100
categories: ["javascript", "arrays"]
permalink: /:categories/:title

---
I while ago I learned about a new way of thinking when it comes to learning (learning inception). It was a game changer for how I’m now going about learning something new.

Avoid unknown unknowns
If you don't know what you don't know, you are lost. I've been guilty of this a lot. I learned JavaScript for a pretty long while before I had a grasp of all the things that is possible to do with this language.

Lets say you want to learn enough about arrays to be completely comfortable working with them.

If you don't know anything about arrays and just dive into the subject head on the task will probably feel much more difficult. How much more is there to know? And how do the thing I'm learning right now relate to the rest?

Instead it's a good idea to learn about what kind of properties an array have. What kinds of methods there is. How many methods there are and which ones are the most valuable to know.

If we know these kind of things we can:

1. *Plan our learning with the the goal in mind.*

2. *The challenge will not seem as big because we actually know whats ahead of us.*

This way of thinking was presented to me by John Somnez in one of his books. Here is his website.

So lets put this principle to use!

Here is a list of all the different methods on the array object.

### Mutator that modify
These methods modify the array:

**Array.prototype.copyWithin()**

Copies a sequence of array elements within the array.

**Array.prototype.fill()**

Fills all the elements of an array from a start index to an end index with a static value.

**Array.prototype.pop()**

Removes the last element from an array and returns that element.

**Array.prototype.push()**

Adds one or more elements to the end of an array and returns the new length of the array.

**Array.prototype.reverse()**

Reverses the order of the elements of an array in place — the first becomes the last, and the last becomes the first.

**Array.prototype.shift()**

Removes the first element from an array and returns that element.

**Array.prototype.sort()**

Sorts the elements of an array in place and returns the array.

**Array.prototype.splice()**

Adds and/or removes elements from an

**Array.Array.prototype.unshift()**

Adds one or more elements to the front of an array and returns the new length of the array.

### Accessor methods
These methods do not modify the array and return some representation of the array.

**Array.prototype.concat()**

Returns a new array comprised of this array joined with other array(s) and/or value(s).

**Array.prototype.includes()**

Determines whether an array contains a certain element, returning true or false as appropriate.

**Array.prototype.indexOf()**

Returns the first (least) index of an element within the array equal to the specified value, or -1 if none is found.

**Array.prototype.join()**
Joins all elements of an array into a string.

**Array.prototype.lastIndexOf()**

Returns the last (greatest) index of an element within the array equal to the specified value, or -1 if none is found.

**Array.prototype.slice()**

Extracts a section of an array and returns a new array.

**Array.prototype.toSource()**

Returns an array literal representing the specified array; you can use this value to create a new array. Overrides the Object.prototype.toSource() method.

**Array.prototype.toString()**

Returns a string representing the array and its elements. Overrides the Object.prototype.toString() method.

**Array.prototype.toLocalString()**

Returns a localized string representing the array and its elements. Overrides the Object.prototype.toLocaleString() method.

### Iteration methods
Arrays that takes functions as arguments.

**Array.prototype.entries()**

Returns a new Array. Iterator object that contains the key/value pairs for each index in the array.

**Array.prototype.every()**

Returns true if every element in this array satisfies the provided testing function.

**Array.prototype.filter()**

Creates a new array with all of the elements of this array for which the provided filtering function returns true.

**Array.prototype.find()**

Returns the found value in the array, if an element in the array satisfies the provided testing function or undefined if not found.

**Array.prototype.findIndex()**

Returns the found index in the array, if an element in the array satisfies the provided testing function or -1 if not found.

**Array.prototype.forEach()**

Calls a function for each element in the array.

**Array.prototype.keys()**

Returns a new Array. Iterator that contains the keys for each index in the array.

**Array.prototype.map()**

Creates a new array with the results of calling a provided function on every element in this array.

**Array.prototype.reduce()**

Apply a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a single value.

**Array.prototype.reduceRight()**

Apply a function against an accumulator and each value of the array (from right-to-left) as to reduce it to a single value.

**Array.prototype.some()**

Returns true if at least one element in this array satisfies the provided testing function.

**Array.prototype.values()**

Returns a new Array. Iterator object that contains the values for each index in the array.

___


I got this list from MDN.

Now we know that the methods on the array object is very much finite! Peh! What a release! Just that simple fact will make learning this feel much more manageable.