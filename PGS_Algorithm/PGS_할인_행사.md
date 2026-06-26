### PGS 할인 행사 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/131127

```python
from collections import Counter

def solution(want, number, discount):
    answer = 0

    want_dict = {}
    for w, n in zip(want, number):
        want_dict[w] = n

    for i in range(len(discount) - 9):

        ten_days_discount = discount[i:i+10]

        discount_counter = Counter(ten_days_discount)
        
        if discount_counter == want_dict:
            answer += 1
            
    return answer

# 테스트를 위한 테스트 케이스
solution(["banana", "apple", "rice", "pork", "pot"],
         [3, 2, 2, 2, 1],
         ["chicken", "apple", "apple", "banana", "rice", "apple", "pork", "banana", "pork", "rice", "pot", "banana", "apple", "banana"])
```