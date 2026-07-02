### PGS 구명보트 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/42885

```python
from collections import deque

def solution(people, limit):
    answer = 0

    people = deque(sorted(people))

    while len(people) > 0:
        people1 = people.pop()
        if people1 <= limit:
            if len(people) == 0:
                answer += 1
                break
            else:
                people2 = people.popleft()

            if people1 + people2 > limit:
                people.appendleft(people2)
                answer += 1
            elif people1 + people2 <= limit:
                answer += 1
    return answer
```