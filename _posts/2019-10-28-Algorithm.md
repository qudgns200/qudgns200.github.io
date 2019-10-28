---
layout: post
title:  Algorithm(20191028)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">다트 게임</span>
(https://programmers.co.kr/learn/courses/30/lessons/17682)
<br>

```java
import java.util.HashMap;

class Solution {
  public int solution(String dartResult) {
		int answer = 0;
		int j=0;
		int start = 0;
		int end = 0;
		HashMap<Integer, Integer> map = new HashMap<Integer, Integer>();
		
		// 문자열 중 숫자 부분을 확인하여 cal(계산 함수) 함수 호출
		for(int i=0; i<dartResult.length(); i++) {
			if(i==0) continue;
			else {
				if(Character.isDigit(dartResult.charAt(i))) {
					// 10은 2자리 정수 이므로 조건문 처리
					if(dartResult.charAt(i)=='0' && dartResult.charAt(i-1)=='1') {
						continue;
					} else {
						end = i-1;
						cal(start, end, dartResult, map, j);
						start = i;
						j++;
					}	
				}
			}
		}
		cal(start, dartResult.length()-1, dartResult, map, j);
		
		for(int i=0; i<map.size(); i++) answer = answer + map.get(i);
		
		return answer;
	}
	
	// start : 정수 시작점
	// end : 다음 다트 정수 지점 앞자리
	// dartResult : 다트 문자열
	// map : 3개의 다트 점수를 더하기 위한 HashMap
	// idx : map index
	public void cal(int start, int end, String dartResult, HashMap<Integer, Integer> map, int idx) {
		for(int i=start; i<=end; i++) {
			// 정수가 10일 경우에 체크하여 10을 입력
			if(i==start) {
				if(dartResult.charAt(i)=='1' && dartResult.charAt(i+1)=='0') {
					map.put(idx, 10);
					i++;
				}
				else map.put(idx, Character.getNumericValue(dartResult.charAt(i)));
			}
			// 다트 문자열 수식 처리
			else {
				if(dartResult.charAt(i) == 'S') continue;
				else if(dartResult.charAt(i) == 'D') map.put(idx, map.get(idx) * map.get(idx));
				else if(dartResult.charAt(i) == 'T') map.put(idx, map.get(idx) * map.get(idx) * map.get(idx));
				else if(dartResult.charAt(i) == '*') {
					map.put(idx, map.get(idx) * 2);
					if(idx != 0) map.put(idx-1, map.get(idx-1) * 2);
				}
				else if(dartResult.charAt(i) == '#') map.put(idx, map.get(idx) * (-1));
			}
		}
	}
}
```
