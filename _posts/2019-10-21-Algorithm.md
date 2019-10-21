---
layout: post
title:  Algorithm(20191021)_Remove_Element
category: Algorithm 
description: 
---

Algorithm_LeetCode_<span class="red">Remove Element</span>
(https://leetcode.com/problems/remove-element/)
<br>

```java
class Solution {
        public int removeElement(int[] nums, int val) {
            ArrayList<Integer> arr = new ArrayList<Integer>();
    	
            for(int i=0; i<nums.length; i++) {
                if(nums[i] != val) {
                    arr.add(nums[i]);
                }
            }

            for(int i=0; i<arr.size(); i++) {
                nums[i] = arr.get(i);
            }

            return arr.size();
        }
}
```
