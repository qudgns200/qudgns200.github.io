---
layout: post
title:  Algorithm(20191031)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">실패율</span>
(https://programmers.co.kr/learn/courses/30/lessons/42889)
<br>

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.HashMap;

class Solution {
	public int[] solution(int N, int[] stages) {
        int[] answer = {};
        
        int i = 1;
        
        // 스테이지를 클리어 한 인원 수
        double count = stages.length;
        
        HashMap<Integer, Double> map = new HashMap<Integer, Double>();
        
        // stages 배열을 돌며 각 stage의 인원 수를 찾고
        // 이를 총인원에서 나눠주어 실패율을 계산
        // 이후 총인원에서 클리어한 실패한 인원들을 빼서
        // 다음 stage의 인워수로 조정
        while(i!=N+1) {
        	int fail=0;
        	for(int j=0; j<stages.length; j++) {
        		if(stages[j] == i) {
        			fail++;
        		}
        	}
        	// 어떠한 stage의 모든 인원이 있을 경우
        	// 총 인원수가 0이 되어 exception이 발생되기에
        	// 조건문 추가
        	if(count<=0) map.put( i, 0.0);
        	else map.put( i, fail/count);

        	i++;
        	count = count - fail;
        }
        
        // Hashmap Value로 정렬
        // List에 Hashmap key들을 담고
        // comparator 함수를 익명함수로 사용하여 
        // 해당 key들에 대한 value를 비교하여 return
        ArrayList<Integer> arr = new ArrayList<Integer>();
        arr.addAll(map.keySet());
        
        Collections.sort(arr, (Comparator)(o1, o2)-> {
        	Object v1 = map.get(o1);
        	Object v2 = map.get(o2);
        	return ((Comparable) v2).compareTo(v1);
        });
        
        answer = new int[arr.size()];
        for(int k=0; k<arr.size(); k++) {
        	answer[k] = arr.get(k);
        }

        return answer;
    }
}
```
