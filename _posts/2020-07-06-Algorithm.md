---
layout: post
title:  Algorithm(20200706)_BAEKJOON
category: Algorithm 
description: 
---

# 💾 Algorithm(BAEKJOON)
🔢 **11399번**<br>
👉 [문제 바로가기](https://www.acmicpc.net/problem/11399)


✨ **입력**<br>
첫째 줄에 사람의 수 N(1 ≤ N ≤ 1,000)이 주어진다. 둘째 줄에는 각 사람이 돈을 인출하는데 걸리는 시간 Pi가 주어진다. (1 ≤ Pi ≤ 1,000)

✨ **출력**<br>
첫째 줄에 각 사람이 돈을 인출하는데 필요한 시간의 합의 최솟값을 출력한다.

```java
import java.util.Arrays;
import java.util.Scanner;

public class Problem_200706_11399 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int[] arr = new int[N];
		int sum = 0;
		int result = 0;
		
		for(int i=0; i<N; i++) {
			arr[i] = sc.nextInt();
		}
		Arrays.sort(arr);

		for(int i: arr) {
			sum += i;
			result += sum;
		}
		System.out.println(result);
	}
}
```
