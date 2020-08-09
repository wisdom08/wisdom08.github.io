---
title: algorithms_20200808
permalink: /docs/algorithms_20200808
parent: algorithms_202008
grand_parent: algorithms
has_children: false
nav_order: 0
---

## 문제

- baekjoon-1110 더하기 사이클
- 조건을 만족할 때까지 계속 더하는 문제

---

### 1. 이해

- input: n (0<=n<=99)
- output: cnt (사이클의 길이)
- 특정 프로세스를 반복적으로 거쳐서 다시 입력값(n)으로 돌아오는 사이클의 길이(cnt)를 구해야한다.

### 2. 계획

- 입력값에서 1의자리 숫자, 10의자리 숫자를 분리해서 sum값 도출.(fN, bN)
- sum값 활용
- 특정 프로세스의 과정을 거친 숫자(결과값)의 자릿값을 위해 10을 곱하고, 10을 나눈다.
- 결과값과 입력값이 같은 경우 루프 중단
- cnt 출력

### 3. 실행

```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);

		int n = sc.nextInt();
		int input = n;
		int sum = 0;
		int cnt = 0;

		do {
			int fNum = n / 10;
			int bNum = n % 10;
			sum = fNum + bNum;
			n = bNum * 10 + (sum % 10);
			cnt++;
		} while (input != n);

		System.out.println(cnt);

	}
}
```

### 4. 회고

- 정답을 도출하지 못해서 다른 사람의 풀이를 보고 난 후에야 풀었습니다.
- 머리속에서 전체적인 과정을 생각하지말고, 각 과정을 작게 쪼개는 게 저한테 필요해 보입니다.
- 처음에 문제를 봤을 때는 어려워서 대체 뭐지? 싶었는데 다른 사람의 풀이를 여러개 보고나서 각 과정을 작게 쪼개고 보니 어려운 문제는 아닌 것 같습니다.
- 다음에 다시 이 문제와 비슷한 문제를 풀게 된다면 다른 사람의 풀이를 보지 않고 풀 수 있게끔 이 문제를 정확하게 이해해야겠습니다.
