### PGS 다음 큰 숫자 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12911

```python
def solution(n):
    N = bin(n)[2:]

    while True:
        n += 1
        N2 = bin(n)[2:]
        if len(N.replace('0', '')) == len(N2.replace('0', '')):
            return n
            break
        else:
            continue
```