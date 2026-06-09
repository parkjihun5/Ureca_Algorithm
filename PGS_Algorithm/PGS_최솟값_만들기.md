### PGS 최솟값 만들기 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12941

```python
def solution(A,B):
    answer = 0

    A = sorted(A)
    B = sorted(B, reverse=True)

    for i in range(len(A)):
        num = A[i] * B[i]
        answer += num

    return answer
```