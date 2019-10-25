---
layout: post
title:  Algorithm(20191025)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">완주하지 못한 선수</span>
(https://programmers.co.kr/learn/courses/30/lessons/42576)
<br>

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;

// 2개의 배열을 List에 담아 순차 정렬 후
// 순차적으로 비교하며 2개의 문자열이 다른 값을 리턴
// 처음 이중 for문으로 제작하였다가 시간 초과로 실패
// 자바 내 클래스를 활용하여 문제 해결

class Solution {
    public String solution(String[] participant, String[] completion) {
        ArrayList<String> arr1 = new ArrayList<String>(Arrays.asList(participant));
		ArrayList<String> arr2 = new ArrayList<String>(Arrays.asList(completion));
		
		Collections.sort(arr1);
		Collections.sort(arr2);
		
		for(int i=0; i<arr2.size(); i++) {
			if(!arr1.get(i).equals(arr2.get(i))) {
				return arr1.get(i);
			}
		}
		
		return arr1.get(arr1.size()-1);
    }
}
```
