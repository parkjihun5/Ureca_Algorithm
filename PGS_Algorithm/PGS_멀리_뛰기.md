### PGS 멀리 뛰기 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12914

```python
def solution(n):
    
    if n <= 2:
        return n
    
    num = [1, 2]

    for _ in range(n-2):
        k = num[-1] + num[-2]
        num.append(k)
    
    answer = num[-1] % 1234567
    return answer
``