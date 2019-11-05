---
layout: post
title:  Algorithm(20191105)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">문자열 압축</span>
(https://programmers.co.kr/learn/courses/30/lessons/60057)
<br>

```java
import java.util.ArrayList;

class Solution {
    public int solution(String s) {
        int answer = s.length();
        int len=1; // 자를 문자열 개수
        
        // 자른 문자열들을 담기 위한 ArrayList
        ArrayList<String> arr = new ArrayList<String>();
        
        // 압축 문자열 저장 ArrayList
        ArrayList<String> brr = new ArrayList<String>();

        // 1. 문자열을 2개 단위부터 문자열 길이 반만큼의 길이까지 자르고 저장
        // 2. 자른 문자열들을 비교하여 중복 개수 저장
        // 3. 저장된 문자열들 길이 비교하여 가장 짧은 문자 길이 리턴
        while(len!=s.length()/2+1) {
        	int compareCnt = 0;
        	int start=0; // 문자열 자르기 전 시작 부분
        	int end=len; // 문자열 자르는 인덱스
        	int temp=1; // 문자열 길이 저장 변수
        	arr.clear();
        	brr.clear();
        	
        	String str=null;
        	
        	// 문자열을 자를 문자열 길이 만큼 잘라서 ArrayList에 저장
        	for(int i=0; i<s.length()/len; i++) {
        		arr.add(s.substring(start, end));
        		start += len;
        		end += len;
        	}
        	
        	// 길이만큼 자르고 남은 문자열들을 ArrayList에 저장
        	if(start<s.length()) arr.add(s.substring(start, s.length()));
        	
        	// 자른 문자열들을 비교하여 개수를 구하여 ArrayList에 저장
        	for(int i=0; i<arr.size(); i++) {
        		if(i==0) str = arr.get(i);
        		else {
        			if(str.equals(arr.get(i))) {
        				temp++;
        			} else {
        				if(temp>1) str = temp+str;
        				brr.add(str);
        				str = arr.get(i);
        				temp=1;
        			}
        		}
        	}
        	
        	// 마지막 인덱스의 문자열을 확인하여 저장
        	if(temp>1) str = temp+str;
        	brr.add(str);
        	
        	// 저장된 문자열 길이 확인
        	for (String string : brr) {
				compareCnt += string.length();
			}
        	
        	// 이전 압축된 문자열의 길이와 비교하여 짧은 길이를 저장
        	if(compareCnt < answer) answer = compareCnt;

        	len++;
        }
        
        return answer;
    }
}
```
