## Remove Duplicates from Sorted Array

[Problem](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

## 描述

设给定已排序数组有n个不同数字，要求将该数组的前n个数字变为按顺序排列的，返回n值

## 约定

*  you must do this by modifying the input array in-place with O(1) extra memory.

## 示例

Example 1:
```
Given nums = [1,1,2],

返回值为2

也就是说数组必须排列为[1,2,X]
```
Example 2:
```
Given nums = [0,0,1,1,1,2,2,3,3,4],

返回 5

也就是说数组必须排列为[0,1,2,3,4,...]
```

## Code

```
class Solution {
    public int removeDuplicates(int[] nums) {
        int pt = 0;
        for (int i = 1; i < nums.length; i++){
            if(nums[i] != nums[pt]) 
                nums[++pt] = nums[i];
        }
        return pt+1;
    }
}
```
老牛逼了速度超 99.88%
