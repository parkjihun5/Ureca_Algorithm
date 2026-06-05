### PGS JadenCase 문자열 만들기 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12951

```python
def solution(s):
    # 1. 정직하게 공백 한 칸 기준으로 쪼개기 (연속 공백 보존)
    words = s.split(' ')

    S = []
    for i in words:
        # i가 빈 문자열('')일 때 .capitalize()를 해도 에러 없이 그대로 ''를 반환합니다.
        s_cap = i.capitalize()
        S.append(s_cap)
        
    # 2. for문이 다 끝나고 마지막에 한 번만 합치기!
    return " ".join(S)
```