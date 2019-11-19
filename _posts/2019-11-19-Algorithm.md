---
layout: post
title:  Algorithm(20191119)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">프린터</span>
(https://programmers.co.kr/learn/courses/30/lessons/42587)
<br>

```java
import java.util.ArrayList;
import java.util.Collections;

class Solution {
    public int solution(int[] priorities, int location) {
        int answer = 1;
        int loc = location;
        ArrayList<Integer> arr = new ArrayList<Integer>();
        for (int i : priorities) arr.add(i);
        
        // 매번 최대값을 확인하여
        // ArrayList의 0번 값과 비교
        // 1. 0번 데이터가 max 일 경우
        //    요청 문서가 맞을 경우 그대로 Loop 종료
        //    아닐 경우 인쇄 횟수 플러스, 0번 데이터 삭제
        //    데이터가 하나씩 땡겨지므로 location도 마이너스
        // 2. 0번 데이터가 max가 아닐 경우
        //    0번 데이터를 저장하였다가 ArrayList에 추가해주고
        //    기존 0번 데이터는 삭제
        //    location이 0이었다면 ArrayList의 끝자리로 변경
        //    아니라면 마이너스
        // 이러한 방식으로 ArrayList가 빌 때가지 반복
        while(!arr.isEmpty()) {
        	int max = Collections.max(arr);
        	
        	if(arr.get(0)==max) {
        		if(loc==0) break;
        		answer++;
        		arr.remove(0);
        		loc--;
        	} else {
        		int temp = arr.get(0);
        		arr.remove(0);
        		arr.add(temp);
        		if(loc==0) loc = arr.size()-1;
        		else loc--;
        	}
        }
        
        return answer;
    }
}   
```
