---
layout: post
title:  Algorithm(20191106)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">탑</span>
(https://programmers.co.kr/learn/courses/30/lessons/42588)
<br>

```java
class Solution {
    public int[] solution(int[] heights) {
        int[] answer = {};
        answer = new int[heights.length];
        
        // 전파를 왼쪽으로만 발사하기에
        // 탑의 위치를 오른쪽으로 옮기며
        // 위치보다 왼쪽에 있는 수신탑이 더 높을 경우에만
        // 탑의 인덱스를 저장
        // 아닐 경우 0으로 리턴
        for(int i=0; i<heights.length; i++) {
        	if(i==0) answer[i] = 0;
        	else {
        		for(int j=i-1; j>=0; j--) {
        			if(heights[i]<heights[j]) {
        				answer[i] = j+1;
        				break;
        			} else answer[i] = 0;
        		}
        	}
        }
        return answer;
    }
}
```
