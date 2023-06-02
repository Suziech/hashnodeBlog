---
title: "[Javascript] findIndex"
datePublished: Fri Jun 02 2023 00:52:30 GMT+0000 (Coordinated Universal Time)
cuid: clidup5pg000909mlfiht7o0s
slug: javascript-findindex
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/YJxAy2p_ZJ4/upload/1a0daf339df244ae0cd5af1c9d58b412.jpeg
tags: javascript, findindex

---

Could you try to solve the below problem?

> Please complete the solution function to return the index of the first occurrence of a negative integer in the given integer list, num\_list. If there are no negative integers, return -1.

```javascript
const num_list = [12, 4, 15, 46, 38, -2, -15] // result  = 5
function solution(num_list) {

}
```

here is my solution :

```javascript
const solution = num_list => num_list.indexOf(num_list.filter(num => num<0)[0])
```

1. filter the element less than 0.
    
2. get the first index of the element from the filtered array.
    
3. find index from the 'num\_list' using 2.
    

and I found out other people used a method called: 'findIndex'

since I'm seeing this method for the first time, I would like to share it in my blog.

Let's see what MDN says

> Array.prototype.findIndex()
> 
> the `findIndex()` method returns the index of the first element in an array that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned.

`findIndex()` helps you find the position (index) of the first element in an array that meets a specific condition. If an element is found that satisfies the condition, the index of that element is returned. If no element satisfies the condition, `-1` is returned.

In summary, `findIndex()` <mark> searches for an element in an array and tells you where it is located, or returns </mark> `-1` <mark> if the element is not found.</mark>

after reading the definition of this method, I realised that `findIndex()` is perfect for the above problem to solve!

because this method is going to get the first element in the array that matches the condition and if no element matches any, it will return -1.

the Snytax would be as below:

> findIndex(callbackFn)
> 
> findIndex(callbackFn, thisArg)

and here's the solution using `findIndex()`

```javascript
const solution = num_list.findIndex(num => num < 0)
```

it seems like much shorter code and simpler!