## Remove Element

[Problem](https://leetcode.com/problems/remove-element/)

## Description

给定一个数组和值 *val* ，要求返回n，n为数组中除了 *val* 剩余的数值【还是看示例比较好懂=。=


## 约束

* Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

## 示例

Example 1:
```
Given nums = [3,2,2,3], val = 3,

函数的返回值为2，此时数组内应为 [2,2,X,X]

It doesn't matter what you leave beyond the returned length.
```
Example 2:
```
Given nums = [0,1,2,2,3,0,4,2], val = 2,

函数的返回值为2，此时数组内应为 [0,1,3,0,4,...]

Note that the order of those five elements can be arbitrary.

It doesn't matter what values are set beyond the returned length.
```

## Code

```
class Solution {
    public int removeElement(int[] nums, int val) {
        int i = 0;
        for(int j = 0; i + j < nums.length;){
            if (nums[i] == val){
                if (nums[i+j] == val) j++;
                else {
                    nums[i] = nums[i+j];
                    nums[i+j] = val;
                    i++;
                }
            }else i++;
        }
        return i;
    }
}
```
>Runtime: 3 ms, faster than 100.00% of Java online submissions for Remove Element.

>Memory Usage: 37.9 MB, less than 8.49% of Java online submissions for Remove Element.
惊了/虽然空间占用也似乎蛮大
