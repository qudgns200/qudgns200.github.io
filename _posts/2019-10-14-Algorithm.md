---
layout: post
title:  Algorithm(20191014)_Reverse_Integer
category: Algorithm 
description: 
---

Algorithm_LeetCode_<span class="red">Reverse Integer</span>
(https://leetcode.com/problems/reverse-integer/)
<br>

```java
class Solution {
    public int reverse(int x) {
        String num = Integer.toString(x);
		StringBuffer sb = new StringBuffer();
        boolean chk = false;
		
		try {
			if(x==0) return 0;
			else
			{
				for(int i=num.length()-1; i>=0; i--)
				{
					if(num.charAt(i)!='-')
					{
						if(num.charAt(i)!='0')
						{
							sb.append(num.charAt(i));
							chk = true;
						}
						else
						{
							if(chk==true) sb.append(num.charAt(i));
						}
					}
				}
				int y = Integer.parseInt(sb.toString());
				
				if(x<0) y = -(y);
				return y;
			}
		}
		catch(NumberFormatException e) {
			return 0;
		}
    }
}
```
<br>
쉬운 문제임에도 문제를 제대로 읽지 않아 많은 시행착오를 겪었다.<br>
overflow에 대한 해결을 원하는 문제였을 줄이야...!!!!<br>
<br><br><br>