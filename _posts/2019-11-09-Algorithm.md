---
layout: post
title:  Algorithm(20191109)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">스킬트리</span>
(https://programmers.co.kr/learn/courses/30/lessons/49993)
<br>

```java
class Solution {
    public int solution(String skill, String[] skill_trees) {
        int answer = 0;

        // skill_trees 만큼 isCorrect 함수를 실행시키고
        // 리턴 값이 True일 때만 가능한 스킬 트리의 개수를 증가
        for(int i=0; i<skill_trees.length; i++) {
        	if(isCorrect(skill, skill_trees[i])) answer++;
        }
        return answer;
    }
	
	public boolean isCorrect(String skill, String skill_tree) {
		
		int beforeSkill = 0;
		int currentSkill = 0;
		boolean skillCheck = true;
		
        // skill_trees의 char 하나씩 skill에서 찾아보며
		// 없는 경우는 계속 진행, 있는 경우 이전 스킬 상태(beforeSkill)의 인덱스를 확인하여
        // 같은 경우 이전 스킬 상태를 증가시켜서 스킬 순서를 확인하고
        // 이전 스킬 상태를 거치지 않는 스킬 트리의 상태인 경우 false를 리턴
		for(int i=0; i<skill_tree.length(); i++) {
			currentSkill = skill.indexOf(skill_tree.charAt(i));
			
			if(currentSkill == -1) continue;
			else if(beforeSkill < currentSkill) {
				skillCheck = false;
				break;
			} else if(beforeSkill == currentSkill) {
				beforeSkill++;
			}
		}
		return skillCheck;
	}
}
```
