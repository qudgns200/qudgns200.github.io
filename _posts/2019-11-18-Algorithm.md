---
layout: post
title:  Algorithm(20191118)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">구명보트</span>
(https://programmers.co.kr/learn/courses/30/lessons/42885)
<br>

```java
import java.util.Arrays;

class Solution {
    public int solution(int[] people, int limit) {
        int answer = 0;
        
        // 최소값을 가지고 최대값을 비교하여
        // limit가 넘을 경우 최대값은 무조건 보트를 혼자 타야함
        // 넘지 않을 경우는 최소값과 최대값 둘이 보트를 탐
        // 넘지 않을 경우에만 최소값의 인덱스를 하나씩 증가 시킴
        Arrays.sort(people);
        int i, j=0;
        for(i=people.length-1; i>j; i--) {
        	if(people[i] + people[j] <= limit) j++;
        	answer++;
        }
        
        if(i==j) answer++;

        return answer;
    }
}
```
