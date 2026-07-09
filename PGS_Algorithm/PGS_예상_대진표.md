### PGS 예상 대진표 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12985

```python
def solution(n, a, b):
    answer = 0
    
    # a와 b가 서로 만나지 않는 한 (경기 번호가 달라 서로 다른 경기를 치르는 한) 계속 반복
    while a != b:
        answer += 1 # 라운드가 올라감
        
        # 다음 라운드 번호 갱신
        a = (a + 1) // 2
        b = (b + 1) // 2
        
    return answer
```