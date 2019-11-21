---
layout: post
title:  Algorithm(20191121)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">카펫</span>
(https://programmers.co.kr/learn/courses/30/lessons/42842)
<br>

```java
class Solution {
    public int[] solution(int brown, int red) {
        int[] answer = new int[2];
        
        int carpet = brown + red;
        int m=3, n=3; // m:가로, n:세로
        
        // brown : 가로*2 + (세로-2)*2
        while(true) {
        	if(carpet%n==0) {
        		m=carpet/n;
        		if(brown == m*2+(n-2)*2) {
        			answer[0] = m;
        			answer[1] = n;
        			break;
        		}
        	}
        	n++;
        }
        
        System.out.println(answer[0] + " " + answer[1]);
        
        return answer;
    }
}
```
