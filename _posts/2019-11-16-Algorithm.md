---
layout: post
title:  Algorithm(20191116)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">오픈채팅방</span>
(https://programmers.co.kr/learn/courses/30/lessons/42888)
<br>

```java
import java.util.ArrayList;
import java.util.HashMap;

class Solution {
    public String[] solution(String[] record) {
        String[] answer = {};
        
        // HashMap : ID와 Nickname을 담기 위한 HashMap
        // ArrayList : Enter, Leave를 담기 위한 ArrayList
        HashMap<String, String> map = new HashMap<String, String>();
        ArrayList<String> arr = new ArrayList<String>();
        
        int count=0;
        
        // 주어진 String 배열을 Loop 돌며 공백으로 Split하고
        // Enter와 Leave 일 때 ArrayList에 행동과 아이디를 저장
        // 그리고 아이디와 닉네임을 HashMap에 저장
        for(int i=0; i<record.length; i++) {
        	String[] temp = record[i].split(" ");
        	if(temp[0].equals("Enter") || temp[0].equals("Leave")) {
        		arr.add(temp[0]);
        		arr.add(temp[1]);
        		if(temp[0].equals("Enter")) {
        			map.put(temp[1], temp[2]);
        		}
        	}
        	else map.put(temp[1], temp[2]);
        }
        
        answer = new String[arr.size()/2];
        
        
        // ArrayList의 2개씩(행동, 아이디)를 Answer에 저장하여 리턴
        for(int i=0; i<arr.size(); i+=2) {
        	if(arr.get(i).equals("Enter")) {
        		answer[count] = map.get(arr.get(i+1)) + "님이 들어왔습니다.";
        	} else {
        		answer[count] = map.get(arr.get(i+1)) + "님이 나갔습니다.";
        	}
        	count++;
        }
        
        return answer;
    }
}
```
