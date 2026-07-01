### PGS 점프와 순간이동 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12980

```python
def solution(n):
    ans = 0
    
    while n > 0:
        if n % 2 != 0:
            n -= 1
            ans += 1
        else:
            n /= 2

    return ans
```