---
title: algorithms_20200818
permalink: /docs/algorithms_20200818
parent: algorithms_202008
grand_parent: algorithms
has_children: false
nav_order: 4
---

## 문제

- BAEKJOON: 11729번 하노이 탑 이동 순서
- 정해진 규칙에 따라 원판들을 첫 번째 장대에서 세 번째 장대로 옮기기

---

### 1. 이해

- 최소의 이동 횟수 도출
- input:
  - 원판의 개수 n
  - 출발 원판 from
  - 이용하는 원판 by
  - 도착원판 to
- output:
  - 첫 째 줄에 옮긴 횟수 k
  - 두 번째 줄부터 수행 과정 출력

### 2. 계획

- 첫 번째 원판에서 제일 밑에 있는 가장 큰 거만 남겨 놓고 두 번째 원판에 다 옮긴다.(세 번째 원판 이용)
- 첫 번째 원판에 남은 걸 세 번째 원판으로 옮긴다.
- 두 번쨰 원판에 있는 것 전부 세 번째 원판위로 쌓는다.(첫 번째 원판 이용)

### 3. 실행

```java
import java.util.Scanner;

public class Main {

	static int k = 0;
	static StringBuilder sb = new StringBuilder();

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();

		hanoi(n, 1, 2, 3);
		System.out.println(k);
		System.out.println(sb);

	}

	private static void hanoi(int n, int from, int by, int to) {
		k += 1;

		if (n == 1) {
			sb.append(from + " " + to + "\n");
		}

		else {
			hanoi(n - 1, from, to, by);
			sb.append(from + " " + to + "\n");
			hanoi(n - 1, by, from, to);
		}
	}
}
```

### 4. 회고

- 재귀함수라는 단어때문이었는지 3개, 4개짜리로 그려가면서 공통점을 찾아보려고 했는데 못찾았습니다.
- 힌트를 몇 번이나 보고난 후에야 이해 했습니다.
- 핵심은 문제를 세분화시켜 원반 n-1개를 이동하는 것과 원반 1개를 이동하는 것을 나눠서 생각해야 합니다. 문제를 세분화시키는 연습을 앞으로 계속 해야겠습니다.
