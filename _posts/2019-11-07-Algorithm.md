---
layout: post
title:  Algorithm(20191107)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">기능 개발</span>
(https://programmers.co.kr/learn/courses/30/lessons/42586)
<br>

```java
import java.util.ArrayList;

class Solution {
    public int[] solution(int[] progresses, int[] speeds) {
        int[] answer = {};
        int cnt=1; // 배포 기능 개수
        int temp1 = (int) Math.ceil((100-progresses[0])/speeds[0]); // 베포 남은 일 수
        int temp2 = 0; // 이전 기능의 남은 배포 일 수와 비교 할 바로 다음 기능 배포 일 수
        ArrayList<Integer> arr = new ArrayList<Integer>(); // 배포 기능 수를 담을 list
        
        // Loop를 돌면서 이전 기능 배포 일 수와 비교하여
        // 이전 배포 일 수가 더 길 경우 cnt를 증가시키고
        // i번째 배포 일 수가 더 길 경우 list에 계산했던 cnt를 대입
        for(int i=1; i<progresses.length; i++) {
        	temp2 = (int) Math.ceil((100-progresses[i])/speeds[i]);
        	
        	if(temp1 >= temp2) cnt++;
        	else {
        		arr.add(cnt);
        		cnt = 1;
        		temp1 = temp2;
        	}
        	
        	if(i==progresses.length-1) arr.add(cnt);
        }
        
        // answer를 정의하고 list의 데이터 삽입
        answer = new int[arr.size()];
        for(int i=0; i<arr.size(); i++) answer[i] = arr.get(i);
        
        return answer;
    }
}
```
