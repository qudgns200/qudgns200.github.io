---
layout: post
title:  Algorithm(20191117)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">124 나라의 숫자</span>
(https://programmers.co.kr/learn/courses/30/lessons/12899)
<br>

```java
class Solution {
  public String solution(int n) {
      String answer = "";
	      int remainder; // 나머지를 저장하기 위한 변수
	      
	      // 숫자가 3개이므로 3으로 계속 나눠주어
	      // 나머지를 뒤에다 계속 붙여주고
	      // 나머지가 0일 경우 124 규칙이므로 4로 remainder를 설정
	      // 몫은 1을 빼서 더 진행
	      while(n>0) {
	    	  remainder = n%3;
	    	  n = n/3;
	    	  
	    	  if(remainder==0) {
	    		  remainder = 4;
	    		  n -= 1;
	    	  }
	    	  
	    	  answer = remainder + answer;
	      }
	      
	      return answer;
  }
}
```
