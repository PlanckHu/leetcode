## Median of Two Sorted Arrays

[题目](https://leetcode.com/problems/median-of-two-sorted-arrays/)

## 题目描述
There are two sorted arrays **nums1** and **nums2** of size **m** and **n** respectively.

有俩数组 nums1 和 nums2 , 长度分别为 m 和 n 

Find the median of the two sorted arrays. The overall run time complexity should be O(log (m+n)).

找到中位数。时间复杂度在O(log (m+n))

You may assume nums1 and nums2 cannot be both empty.

可假设俩数组为非空


## 约定

1. 数组非空
2. 时间复杂度在O(log (m+n))

## 示例

Example 1:
```
  nums1 = [1, 3]
  nums2 = [2]

  The median is 2.0
```
Example2:
```
  nums1 = [1, 2]
  nums2 = [3, 4]

  The median is (2 + 3)/2 = 2.5
```

## 解答

```Java
  // 最直接的方法/ 重排入一个数组然后取中间一/两个数
  class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int length = nums1.length + nums2.length;
        int[] temp = new int[length];
        int m = 0;
        int n = 0;
        for (int i = 0; i < length; i++) {
            if (m >= nums1.length) {
                temp[i] = nums2[n++];
            } else if (n >= nums2.length) {
                temp[i] = nums1[m++];
            } else {
                temp[i] = (nums1[m] < nums2[n]) ? nums1[m++] : nums2[n++];
            }
        }
        int cnt;
        if (length % 2 == 0) {
            cnt = length / 2 - 1;
            return (double) (temp[cnt] + temp[cnt + 1]) / 2;
        }else{
            cnt = length / 2;
            return temp[cnt];
        }
    }
}

```
