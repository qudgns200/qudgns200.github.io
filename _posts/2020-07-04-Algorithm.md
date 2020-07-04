---
layout: post
title:  Algorithm(20200704)_BAEKJOON
category: Algorithm 
description: 
---

# 💾 Algorithm(BAEKJOON)
🔢 **4344번**<br>
👉 [문제 바로가기](https://www.acmicpc.net/problem/4344)


✨ **입력**<br>
첫째 줄에는 테스트 케이스의 개수 C가 주어진다.

둘째 줄부터 각 테스트 케이스마다 학생의 수 N(1 ≤ N ≤ 1000, N은 정수)이 첫 수로 주어지고, 이어서 N명의 점수가 주어진다. 점수는 0보다 크거나 같고, 100보다 작거나 같은 정수이다.

✨ **출력**<br>
각 케이스마다 한 줄씩 평균을 넘는 학생들의 비율을 반올림하여 소수점 셋째 자리까지 출력한다.

```java
import java.util.Scanner;

public class Problem_200704_4344 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int C; // Test Case
		int N; // Students
		
		Scanner scan = new Scanner(System.in);
		C = scan.nextInt();
		
		String[] result = new String[C];
		
		for(int i=0; i<C; i++) {
			N = scan.nextInt();
			int[] scoreArr = new int[N]; // N명의 점수를 담기 위한 배열
			int sum = 0; // 학생들 점수의 합계
			int avg = 0; // 학생들 점수의 평균
			int count = 0; // 평균을 넘는 학생들 수
			for(int j=0; j<N; j++) {
				scoreArr[j] = scan.nextInt();
				sum += scoreArr[j]; // 합계 구하기
			}
			avg = sum/N; // 평균 구하기
			for(int k=0; k<N; k++) {
				if(scoreArr[k] > avg) {
					count++; // 학생의 점수가 평균을 넘으면 카운트 증가
				}
			}
			double n2 = Math.pow(10.0, 3); // 소수 셋째자리까지 반올림 하기 위함
			double output = (Math.round((count/(double)N*100)*n2)/n2);
			// double형 변환 후 100을 곱하여 % 하고 10의 세제곱으로 셋째자리로 반올림
			result[i] = String.format("%.3f", output) + "%";
		}
		for(int m=0; m<C; m++) {
			System.out.println(result[m]);
		}
	}
}

```
