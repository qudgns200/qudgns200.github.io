---
layout: post
title:  Algorithm(20191018)_Remove_Duplicates_from_Sorted_Array
category: Algorithm 
description: 
---

Algorithm_LeetCode_<span class="red">Remove Duplicates from Sorted Array</span>
(https://leetcode.com/problems/remove-duplicates-from-sorted-array/)
<br>

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        ArrayList<Integer> list = new ArrayList<Integer>();
    	
    	for(int i=0; i<nums.length; i++) {
        	if(!list.contains(nums[i])) {
        		list.add(nums[i]);
        	}
        }
        
        for(int i=0; i<list.size(); i++) {
        	nums[i] = list.get(i);
        }
        return list.size(); 
    }
}
```
