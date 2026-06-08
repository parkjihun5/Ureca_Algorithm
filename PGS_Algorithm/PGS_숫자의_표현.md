### PGS 숫자의 표현 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12924

```python
def solution(n):
    # 1부터 n까지 2씩 건너뛰며(즉, 홀수만) n의 약수인지 확인하고 개수를 셈
    answer = len([i for i in range(1, n + 1, 2) if n % i == 0])
    return answer
```