---
layout: post
title:  Algorithm(20191112)_Programmers
category: Algorithm 
description: 
---

Algorithm_programmers_<span class="red">다리를 지나는 트럭</span>
(https://programmers.co.kr/learn/courses/30/lessons/42583)
<br>

```java
import java.util.Arrays;

class Solution {
    public int solution(int bridge_length, int weight, int[] truck_weights) {
        int answer = 0;
		int index = 0;
		int sum = 0;

		// Bridge 크기만큼 배열 생성 후 0으로 배열 채움
		int[] arr = new int[bridge_length];
		Arrays.fill(arr, 0);

		// 트럭이 다 지나갈 때까지 while문을 실행
		// 무게의 합이 0일 때는 0번째 다리 배열에 index의 트럭 무게를 대입하고 index 및 answer(시간 초)를 증가
		// 무게의 합이 0이 아닐 때는 다리 배열의 마지막 값을 체크하여 0이 아닐 경우에는 합계에서 그만큼 빼주고
		// for문을 돌려 다리 배열의 트럭들을 한 칸씩 이동 시킴
		// 그리고 다음 트럭과의 무게를 계산하여 다리 배열의 첫번째로 이동 시킬 지 결정하고
		// answer을 증가시킴
		while (index != truck_weights.length) {
			if (sum == 0) {
				arr[0] = truck_weights[index];
				sum += truck_weights[index];
				index++;
				answer++;
			} else {
				if (arr[arr.length - 1] != 0) {
					sum -= arr[arr.length - 1];
				}
				
				for (int i = arr.length - 2; i >= 0; i--) {
					arr[i + 1] = arr[i];
					arr[i] = 0;
				}

				if (sum + truck_weights[index] <= weight) {
					arr[0] = truck_weights[index];
					sum += truck_weights[index];
					index++;
				}
				answer++;
			}
		}
		
		// 다리 배열에 남아있는 차 중 제일 끝에 있는 차의 위치를 찾아
		// 다리 길이에서 해당 위치를 빼서 시간을 계산
		for (int i = 0; i < arr.length; i++) {
			if (arr[i] != 0) {
				answer += bridge_length - i;
				break;
			}
		}
		return answer;
    }
}
```
