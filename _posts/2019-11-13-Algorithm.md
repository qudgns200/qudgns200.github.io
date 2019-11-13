---
layout: post
title:  Algorithm(20191113)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">영어 끝말 잇기</span>
(https://programmers.co.kr/learn/courses/30/lessons/12981)
<br>

```java
import java.util.HashSet;

class Solution {
    public int[] solution(int n, String[] words) {
        int[] answer = {};
        answer = new int[2];
        int dupIdx=-1;
        
        // HashSet을 이용하여 중복된 데이터를 찾음
        HashSet<String> setWords = new HashSet<String>();
        for(int i=0; i<words.length; i++) {
        	boolean isDup = setWords.add(words[i]);
        
        	if(!isDup) {
        		dupIdx = i+1;
        		break;
        	}
        }
        
        // dupIdx가 -1이 아니면 중복된 문자열이 존재하기 때문에
        // dupIdx를 사람 수로 나누었을 때
        // 0이면 n번째 사람
        // 0이 아니면 나머지 번째 사람
        if(dupIdx!=-1) {
        	int person = dupIdx%n;
        	if(person==0) {
        		answer[0] = n;
        		answer[1] = dupIdx/n;
        	} else {
        		answer[0] = person;
        		answer[1] = dupIdx/n+1;
        	}
        	// dupIdx가 -1인 경우에는 중복값이 존재하지 않기 때문에
        	// 모든 문자열을 loop 돌며 끝말잇기가 잘 진행되었는지 확인
        } else {
        	for(int i=1; i<words.length; i++) {
        		if(words[i-1].charAt(words[i-1].length()-1) !=
        				words[i].charAt(0)) {
        			if((i+1)%n==0) {
        				answer[0] = n;
        				answer[1] = (i+1)/n;
        				break;
        			} else {
        				answer[0] = (i+1)%n;
        				answer[1] = (i+1)/n+1;
        				break;
        			}
        		} else {
        			answer[0] = 0;
    				answer[1] = 0;
        		}
        	}
        }

        return answer;
    }
}
```
