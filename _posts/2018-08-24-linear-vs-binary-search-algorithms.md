---
layout: post
title:  "Linear vs binary search algorithms"
date:   2018-08-24 20:01:19 +0100
categories: ["algorithms", "javascript"]
permalink: /:categories/:title
---


Search algorithms are useful for when we encounter problems that require... searching! It could be a list of names. Or an array of usernames. Or maybe a list of  reptiles?

### Linear search (also known as stupid search)
Linear search is an algorithm that checks every item in a list until it finds a match and returns the position.

It is possible that the number of operations increases just as much as the number of inputs. In other words the worst-case time complexity of this algorithm is O(log n). Imagine that the input is an array with the length of one million. In the worst case the algorithm have to look at all the one million items. Not very smart...

This algorithm is not very fast and I don't blame it for it. Why? It's basically just a loop.
```
const reptiles = [ 'agama', 'alligator', 'chameleon',
	'chuckwalla', 'crocodile','gecko', 'gila monster', 'iguana',
 	'lizard', 'monitor', 'skink', 'snake', 'tortoise', 'turtle' ];

function simple_search(arr, toFind) {
	for (let i = 0; i < arr.length; i++) {
		if (arr[i] === toFind) return i;
	}
	return null;	
}

console.log(simple_search(reptiles, 'turtle')); // logs: 13
```
In this example the algorithm finds the item in 14 iterations.

### Binary search
This search algorithm is very fast, it has a run time complexity of O(log n). The array have to be ordered for it to work.
```
const reptiles = [ 'agama', 'alligator', 'chameleon',
  'chuckwalla', 'crocodile','gecko', 'gila monster', 'iguana',
  'lizard', 'monitor', 'skink', 'snake', 'tortoise', 'turtle' ];

function binary_search(arr, toFind) {
  let lowIndex = 0;
  let highIndex = arr.length - 1;
  
  while (lowIndex <= highIndex) {
    // recalculates midIndex for every iteration
    let midIndex = Math.floor((lowIndex + highIndex)/2);
    let guess = arr[midIndex];

    if (guess == toFind) {
      return midIndex;
    }
    // adjust search area
    if (guess > toFind) {
      highIndex = midIndex -1;
    } else {
      lowIndex = midIndex + 1;
    }
  }
  return null;
}

console.log(binary_search(reptiles, 'turtle')); // logs: 13
```
Before the loop begins the lowest end of the search range is 0 and the highest end is the length of the array.

For every iteration of the loop the program compares the item with an index that is in middle of the search range to the item it is are searching for. In this example the first guess would be "gila monster".

It is not correct, so it then continues to check if the guess is greater or smaller than the item we want to find.

If the the item is greater than the guess we adjust the lower end of the search range to be midIndex + 1 (because we have already checked the item at that index).

If the item is smaller than the guess we adjust the higher end of the search range to be midIndex - 1.

On the next iteration the program will check the item that is in the middle of the new search range.

We do this until the item is found and the position of that item is returned, or we run out of items, in that case the item is not in the array and the function returns null.

For every iteration of the loop we eliminate haft of the items! Even though the item we are looking for in this example is at the very end of the array we find it in only 4 iterations (compared to 14 iterations with stupid search).

But the brilliancy of binary search really shows when the size of the input gets larger. If the names of all the people in the world was written down in order, binary search will find the position in maximum 35 operations. With linear search the number of operations could be the same as the amount of people in the world.

This is an example of that the run time of algorithms grows in different rates. The speed of a algorithm is not measured in seconds, but in the number of operations and how fast that number grows as the input gets larger. We get this information from the Big O notation.

[This video explanes Big O notation pretty nice.](https://www.youtube.com/watch?v=v4cd1O4zkGw&t=1s)

Until next time.



