---
layout: post
title:  Algorithm(20191102)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">모의고사</span>
(https://programmers.co.kr/learn/courses/30/lessons/42840)
<br>

```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.Collections;
import java.util.HashMap;

class Solution {
    public int[] solution(int[] answers) {
        int[] answer = {};
        
        // 수포자가 찍는 방식 저장
        int[] n1 = {1,2,3,4,5};
        int[] n2 = {2,1,2,3,2,4,2,5};
        int[] n3 = {3,3,1,1,2,2,4,4,5,5};
        
        // 수포자 점수를 체크하기 위한 Hashmap 선언
        HashMap<String, Integer> map = new HashMap<String, Integer>();
        map.put("n1", 0);
        map.put("n2", 0);
        map.put("n3", 0);
        
        // 수포자 배열의 인덱스를 체크하기 위한 변수
        int idx1=0, idx2=0, idx3=0;
        
        // 문제에 대한 답이 맞을 경우 Hashmap의 해당 Value를 1 더해줌
        // 각 수포자 배열의 길이를 확인하여 배열 인덱스 초기화 시켜줌
        for(int i=0; i<answers.length; i++) {
        	if(n1[idx1]==answers[i]) map.put("n1", map.get("n1")+1);
        	if(n2[idx2]==answers[i]) map.put("n2", map.get("n2")+1);
        	if(n3[idx3]==answers[i]) map.put("n3", map.get("n3")+1);
        	
        	idx1++;
        	idx2++;
        	idx3++;
        	
        	if(idx1==n1.length) idx1=0;
        	if(idx2==n2.length) idx2=0;
        	if(idx3==n3.length) idx3=0;
        }
        
        // Collection을 활용하여 최대값을 찾고 
        // ArrayList를 선언하여 최대값과 비교하여 데이터를 저장
        Collection values = map.values();
        int max = (int) Collections.max(values);

        ArrayList<Integer> arr = new ArrayList<Integer>();
        if(map.get("n1")==max) arr.add(1);
        if(map.get("n2")==max) arr.add(2);
        if(map.get("n3")==max) arr.add(3);

        // ArrayList의 길이만큼 리턴 배열을 초기화 시키고 데이터 저장
        answer = new int[arr.size()];
        for(int i=0; i<arr.size(); i++) answer[i] = arr.get(i); 
        
        return answer;
    }
}
```
