---
layout: post
title:  Algorithm(20191030)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">비밀지도</span>
(https://programmers.co.kr/learn/courses/30/lessons/17681)
<br>

```java
class Solution {
  public String[] solution(int n, int[] arr1, int[] arr2) {
		String[] answer = {};
		answer = new String[n];
		
		// OR 비트연산자 수행
		// 문제에 맞게 1-># / 0->공백 으로 처리
		for(int i=0; i<arr1.length;i++) {
			answer[i] = String.format
					("%" + n + "s", Integer.toBinaryString(arr1[i] | arr2[i]))
							.replace("1", "#")
							.replace("0", " ");
		}
		
		return answer;
	}
}
```
