---
layout: post
title:  Algorithm(20191016)_Longest_Common_Prefix
category: Algorithm 
description: 
---

Algorithm_LeetCode_<span class="red">Longest Common Prefix</span>
(https://leetcode.com/problems/longest-common-prefix/)
<br>

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
		int i=0;
		String result = null;
		
		if(strs.length == 0) result = "";
		else {
			result = strs[i].toString();
			if(result.length()==0 || result.isEmpty()) result = "";
			else {
				for(i=1; i<strs.length;i++) {
					result = returnPrefix(strs[i], result);
				}
			}
		}
		return result;
	}
	
	public String returnPrefix(String strs, String temp) {
		int i=0,j=0;
		StringBuffer sb = new StringBuffer();
		sb.setLength(0);
		while(i < temp.length() && j < strs.length()) {
			if(temp.charAt(i)==strs.charAt(j)) {
				sb.append(temp.charAt(i));
			} else break;
            i++; j++;
		}
		if(sb.length() == 0) sb.append("");
		
		return sb.toString();
	}
}
```
