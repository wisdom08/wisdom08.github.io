---
title: algorithms_20200811
permalink: /docs/algorithms_20200811
parent: algorithms_202008
grand_parent: algorithms
has_children: false
nav_order: 1
---

## 문제

- LEETCODE-1. Two Sum
- Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.
- You may assume that each input would have **_exactly_** one solution, and you may not use the *same* element twice.

---

### 1. 이해

- 주어진 정수 배열에서 더하면 특정 타겟이 되는 두 정수 반환하기

### 2. 계획

- 첫 번째 배열값부터 차례대로 이중 for문을 이용해서 나머지 값들과 하나씩 더해보자

### 3. 실행

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] answer = new int[2];
        for(int i=0; i<nums.length;i++){
            for(int j=i+1; j<nums.length;j++){
                if(nums[i]+nums[j] == target){
                    answer[0] = i;
                    answer[1] = j;
                    break;
                }
            }
        }
        return answer;
    }
}
```

### 4. 회고

- 다른 사람들의 풀이를 보니 haspmap을 주로 사용하는데 봐도 잘모르겠습니다.
- 이번 문제는 그렇게 어렵지 않았는데, 이 방식은 효율이 좀 떨어지는 것처럼 느껴집니다.
