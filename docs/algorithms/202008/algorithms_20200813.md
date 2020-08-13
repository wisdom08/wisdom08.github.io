---
title: algorithms_20200813
permalink: /docs/algorithms_20200813
parent: algorithms_202008
grand_parent: algorithms
has_children: false
nav_order: 3
---

## 문제

- LEETCODE - 66. PLUS ONE
- Given a **non-empty** array of digits representing a non-negative integer, increment one to the integer.
- The digits are stored such that the most significant digit is at the head of the list, and each element in the array contains a single digit.
- You may assume the integer does not contain any leading zero, except the number 0 itself.

---

### 1. 이해

- input: [8, 8, 9], [9, 9, 9]
- output: [8, 9, 0], [1, 0, 0, 0]
- 배열값들을 하나의 숫자로 보고 간단하게 1을 더하는 거다.
- 핵심은 9가 오는 경우 1을 올려주는 거고, 마지막에 배열의 사이즈를 하나 늘려서 제일 앞 배열 값에 1을 넣어주는 거다.

### 2. 계획

- for문 돌려서 자리값이 9인 경우와 9가 아닌 경우로 나눈다.
- 9가 아니면 1더하고 그대로 리턴
- 9인 경우 그 값은 0이 되고, 다시 for문으로 들어간다.
- 배열 사이즈 조정해서 제일 앞에 1을 넣는다.

### 3. 실행

```java
class Solution {
    public int[] plusOne(int[] digits) {
        if(0==digits.length){
            return digits;
        }

        for(int i=digits.length-1; i>=0; i--){
            if(digits[i]!=9) {
                digits[i]++;
                return digits;
            } else {
                digits[i] = 0;
            }
        }
        int[] result = new int[digits.length+1];
        result[0] = 1;
        return result;
    }
}
```

### 4. 회고

- 주어진 배열을 [9,9,9]로 생각하고 문제를 풀려고 했는데 어려웠습니다.
- 간단해보이기도 하고, easy level 이어서 쉽게 풀 수 있을 줄 알았는데 쉽지 않았습니다.
- 배열의 사이즈를 늘린다는 것도 접근하지 못했고, 그 배열의 0번째 값에 1을 넣는다는 것도 전혀 생각하지 못했습니다.
