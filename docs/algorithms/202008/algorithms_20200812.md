---
title: algorithms_20200812
permalink: /docs/algorithms_20200812
parent: algorithms_202008
grand_parent: algorithms
has_children: false
nav_order: 2
---

## 문제

- BAEKJOON-2675
- 문자열 반복

---

### 1. 이해

- input
  - 문자열 S(길이는 1~20),
  - 반복 횟수 R(1 ≤ R≤ 8))
  - \*\*\*\* 테스트 케이스의 개수 T(1 ≤ T ≤ 1,000)
- output: P = S \* R

### 2. 계획

- 문자열을 chra 배열에 담아서 하나씩 루프 돌면서 더하자.
- 이중FOR문 이용

### 3. 실행

```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);

		int test = sc.nextInt();
		for (int k = 0; k < test; k++) {

			int num = sc.nextInt();
			String S = sc.next();
			String result = "";

			char[] ch = S.toCharArray();

			for (int i = 0; i < ch.length; i++) {
				for (int j = 0; j < num; j++) {
					result += ch[i];
				}
			}
			System.out.println(result);
		}

	}
}
```

### 4. 회고

- '문제 너무 쉽네'라고 생각하면서 STS에서 예제 출력값이랑 똑같이 나오는 거 확인하고 백준에 돌렸는데 계속 실패가 결과로 나왔습니다. 그 이유가 문제에서 입력 부분에 테스트 케이스의 숫자가 주어진다고 적혀있는데 그 부분을 놓쳤습니다. 바보같이 시간을 허비했네요. 문제를 더 꼼꼼히 읽어야 겠습니다.
- 문자열 s 를 입력받을 때 습관적으로 자주 사용하는 nextLine()을 이용했는데 에러가 발생했습니다. 이것도 문제에서 s가 공백을 구분되어 주어진다고 명시되어 있었습니다. nextLine()의 경우 엔터 값을 입력 받을 때 까지를 기준으로 한 줄을 읽어버립니다. 즉, 반복횟수인 숫자와 문자열 사이에 있는 공백까지 읽어버려서 에러가 나타나는 것입니다. 그래서 이런 경우, 반드시 공백을 기준으로 하나의 문자열만 읽어들이는 next()로 문자열을 입력받아야 합니다. 차이를 알고있으면서도 왜 안되는지 한참을 헤맸네요. 알고리즘이 코드를 짜는 데도 도움이 된다고 하던데 정말 그럴 것 같기도 하네요.
