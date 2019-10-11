---
layout: post
title:  "Indexof() method"
date:   2018-06-24 20:01:19 +0100
categories: ["javascript", "methods"]
permalink: /:categories/:title
---

The indexOf() method is great for finding out if a string or an array contains a value that you are looking for.

### Using it on arrays

The indexOf() method searches the array for the value that you specify inside the parentheses. The search goes from the lowest index to the highest and will only return the index of the first match.

In this example we check for the value “crab”. Only the index of the first “crab” is returned, the “crab” on index 5 is ignored.
```
const beach = ['sand', 'sand', 'crab', 'sand', 'sand', 'crab', 'sand']

const mySearch = beach.indexOf(“crab”);

console.log(mySearch); // 2
```
But the indexOf() method also takes a second argument: a search value that specifies from what index to start the search. If you don't specify this value it’s 0 by default.
```
const beach = ['sand', 'sand', 'crab', 'sand', 'sand', 'crab', 'sand']

const mySearch = beach.indexOf(“crab”, 3);

console.log(mySearch);  // 5
```
### Using it on strings

The indexOf() method works in the same fashion on strings.

It will return the index of only the first character of the searched string.
```
var string = "Luke, this line is highly misquoted.";

var mySearch = str.indexOf("highly");

console.log(mySearch) // 19
```
### Finnaly: find out if searched value exist.

So why is this method useful? We can use it to find out if a value we are looking for exist in a string or array.

If the value exists, the index of that value is returned. But if the value is not on the string/array the indexOf() method will return -1.
```
const myPocket = ['keys', 'wallet', 'phone', 'lint'];

const mySearch = myPocket.indexOf('Ice cream money');

console.log(mySearch); //-1
```
Now we can check if the value exist with an if statement like this.

```
const beach = ['sand', 'sand', 'crab', 'sand', 'sand', 'crab', 'sand']

if (beach.indexOf(‘starfish’) >=  0) {
	console.log(‘Yep, there is at least one star fish on this beach!’);

} else {
	console.log(‘Sorry, no starfish here,’);
}
```