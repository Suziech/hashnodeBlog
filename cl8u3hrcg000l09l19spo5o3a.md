# [JavaScript] Running Sum of 1d Array

# Problem Statement
- Given an array nums. We define a running sum of an array as `runningSum[i] = sum(nums[0]…nums[i])`. Return the running sum of nums.

# Example

 > Input: nums = [1,2,3,4]

> Output: [1,3,6,10]

> Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].

******

> Input: nums = [3,1,2,10,1]

> Output: [3,4,6,16,17]

******

> It was not easy for me but I've found the way to solve! since I push the number to the new array which is `result`, I simply decided to add the number from that array and voila! 

# My solution
```
const runningSum = nums => {
    result=[];
    for(let i=0; i<nums.length; i++){
        i === 0 ? result.push(nums[i])
        : result.push(nums[i] + result[i-1])
    }
    return result;
}

```


