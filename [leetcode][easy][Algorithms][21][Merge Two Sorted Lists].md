## Merge Two Sorted Lists

[Problem](https://leetcode.com/problems/merge-two-sorted-lists/submissions/)

## Description

Merge two sorted linked lists and return it as a new list.

## Example
```
Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4
```

## Submission
这样的结果似乎是挺快的，就是挺占空间
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        ListNode head = null;
        ListNode mid = null;
        while(l1 != null || l2 != null){
            ListNode temp = null;
            if (l1 == null ){
                temp = l2;
                l2 = l2.next;
            }else if(l2 == null){
                temp = l1;
                l1 = l1.next;
            }else{
                if(l1.val<l2.val){
                    temp = l1;
                    l1 = l1.next;
                }else{
                    temp = l2;
                    l2 = l2.next;
                } 
            }
            if(head == null){
                head = temp;
                mid = head;
            }else{
                mid.next = temp;
                mid = mid.next;
            }
        }
        return head;
    }
}
```
