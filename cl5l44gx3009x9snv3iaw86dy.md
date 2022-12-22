# [JavaScript]filter / CallbackFunction /

# How to use **filter** in JavaScript
arrayName.*filter*((element, index) => element !== arr[index+1];

```
const arr =[1,1,2,2,3,3];

const answer = arr.filter((x,y) => x !== arr[y+1]);

console.log(answer);

//expacted result : [1,2,3]
``` 

x -> value (ex. 1)
y -> index (ex. [0])

filter will scan all the elements in the array and filter which is matched with the condition.