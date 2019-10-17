---
layout: post
title:  Algorithm(20191017)_Merge_Two_Sorted_Lists
category: Algorithm 
description: 
---

Algorithm_LeetCode_<span class="red">Merge Two Sorted Lists</span>
(https://leetcode.com/problems/merge-two-sorted-lists/)
<br>

```java
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
        ListNode l3 = new ListNode(0);
        ListNode head = l3;
        boolean b1 = true, b2 = true;
        if(l1==null) b1=false;
        if(l2==null) b2=false;
        
        while(b1 != false || b2 != false) {
     	
        	if(b1==true && b2==true) {
        		if(l1.val <= l2.val) {
        			head.next = new ListNode(l1.val);
        			if(l1 != null) l1 = l1.next;
        		}
        		else {
        			head.next = new ListNode(l2.val);
        			if(l2 != null) l2 = l2.next;
        		}
        	} else if(b1==false && b2==true) {
    			head.next = new ListNode(l2.val);
    			if(l2 != null) l2 = l2.next;
        	} else if(b1==true && b2==false) {
    			head.next = new ListNode(l1.val);
    			if(l1 != null) l1 = l1.next;
        	}
        	
            if(l1==null) b1=false;
            if(l2==null) b2=false;

        	head = head.next;
        }
        return l3.next;
    }
}
```
