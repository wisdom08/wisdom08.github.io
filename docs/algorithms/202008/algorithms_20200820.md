---
title: algorithms_20200820
permalink: /docs/algorithms_20200820
parent: algorithms_202008
grand_parent: algorithms
has_children: false
nav_order: 5
---

## 문제

- BAEKJOON: 2844번 알람시계
- 45분 일찍 알람 설정하기

---

### 1. 이해

- input: 두 개의 정수 (0 ≤ H ≤ 23, 0 ≤ M ≤ 59)
- output: 45분을 빼는 과정을 거친 후의 두 개의 정수

### 2. 계획

- m 을 기준으로 생각해보자
  - m이 45보다 작다면?
    - m-45+60
    - h-1 (1을 빼고 나서 h가 음수면? 23으로)
  - m이 45보다 크다면?
    - m-45
    - h는 그대로

### 3. 실행

```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int h = sc.nextInt();
		int m = sc.nextInt();

		if (m < 45) {
			m = m - 45 + 60;
			h -= 1;

			if (h < 0) {
				h = 23;
			}
		} else {
			m -= 45;
		}

		System.out.println(h + " " + m);

	}

}
```

### 4. 회고

- 쉽게 풀었다. 기분 좋다.
- 근데 108ms 가 걸렸는데 자바코드 기준으로 1등의 시간은 68ms 다. 내 코드가 거의 1.5배 느리다.
- 자세히 보지는 않았는데 68ms 가 소요된 다른 사람들의 코드를 훑어보니 코드에 전부 BufferedReader와 parseInt가 보인다. BufferedReader의 stream이 Scanner 보다 짧은건가 추측하고 일단 오늘은 끝. 다음에 기억나면 써먹어봐야겠다.
