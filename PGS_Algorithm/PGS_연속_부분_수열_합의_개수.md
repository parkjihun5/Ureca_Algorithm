### PGS 연속 부분 수열 합의 개수 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/131701

```python
def solution(elements):
    n = len(elements)

    extended = elements * 2
    
    numbers = set()

    for i in range(n):
        
        for count in range(1, n + 1):
            
            sub_list = extended[i : i + count]

            numbers.add(sum(sub_list))

    return len(numbers)
```