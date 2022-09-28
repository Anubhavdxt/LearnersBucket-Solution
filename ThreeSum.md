# Three Sum

<h2 style="color: Orange">MEDIUM</h2>

## Question

Given an array of integers `nums` and an integer `target`, check if there are three numbers in the array such that they add up to `target`.

You may assume that each input would have **exactly one solution**, and you may not use the same element twice.

You should return `true` or `false`.

### Example 1

Input: nums = [1, 2, 3, 5, 6, 11, 15, 16, 17, 18], target = 20  
Output: `true`  
Output: Because nums[1] + nums[2] + nums[6] == 20, we return `true`.

### Example 2

Input: nums = [1, 2, 3, 5, 6, 11, 15, 16, 17, 18], target = 90  
Output: `false`  
Output: There are no triplets which sum up to the given target, thus we return `false`.  

### Follow-up

Can you come up with an algorithm that is less than `O(n^2)` time complexity?

## Solution

**Time Complexity** - `O(n)^2`

``` JS
return function threeSum(nums, target) {
  for(let i = 0; i < nums.length; i++){
    let temp = [...nums];
    temp.sort((a,b) => a - b);
    let l = 0, r = temp.length - 1;
    let el = temp[i];
    while(l <= r){
      let sum = temp[l] + temp[r];
      if(sum === target - el) return true;
      else if(sum < target - el) l++;
      else r--;
    }
    return false;
  }
};
```
