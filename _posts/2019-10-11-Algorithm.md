---
layout: post
title:  Algorithm(20191011)_AddTwoNumbers
category: Algorithm 
description: 
---

Algorithm_LeetCode_<span class="red">Add Two Numbers</span>
(https://leetcode.com/problems/add-two-numbers/)
<br>

```java
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode l3 = new ListNode(0);
		ListNode head = l3;

		int i=0;    
		int ret=0;
		
		while(l1 != null || l2 != null) 
		{
            int x,y;
            if(l1==null) x = 0; else x=l1.val;
            if(l2==null) y = 0; else y=l2.val;
			ret = x + y + i;
            i = ret / 10;
            
            head.next = new ListNode(ret%10);
            head = head.next;
            
            if(l1!=null) l1 = l1.next;
            if(l2!=null) l2 = l2.next;
		}
		
		if(i>0) head.next = new ListNode(i);
        
        return l3.next;
    }
}
```
<br>
무수한 실패를 반복하며 해결..<br>
ListNode에 직접 데이터들을 때려넣었더니 되지 않아<br>
참조로 변경 후 해결..<br><br><br>

### <Strong>실패 이미지<Strong>..<br>
![]({{site.baseurl}}/assets/img/Algorithm(20191011).jpg)


