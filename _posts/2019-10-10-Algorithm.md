---
layout: post
title:  Algorithm(20191010)_TwoSum
category: Algorithm 
description: 
---

-------------------------------------------------------

#### Algorithm_LeetCode_<span class="red">TwoSum</span>
Description : https://leetcode.com/problems/two-sum/

-------------------------------------------------------

#### Code snippet

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int i=0, j=0;
        int[] twoSum = new int[2];
        for(i=0;i<nums.length-1;i++)
        {
            for(j=i+1;j<nums.length;j++)
            {
                if(nums[i]+nums[j]==target)
                {
                    break;
                }
            }
            if(j!=nums.length) break;
        }
        twoSum[0] = i;
        twoSum[1] = j;
        return twoSum;
    }
}
```
