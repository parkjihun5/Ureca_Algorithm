### PGS 캐시 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/17680

```python
from collections import deque

def solution(cacheSize, cities):
    answer = 0
    # 1. 예외 처리: 캐시 크기가 0이면 볼 것도 없이 전부 5초씩 걸림
    if cacheSize == 0:
        return len(cities) * 5
        
    # 지훈 님의 무기: maxlen을 지정한 deque 바구니 만들기
    # 이렇게 하면 len(cache) == cacheSize 일 때 알아서 맨 앞이 빠짐
    cache = deque(maxlen=cacheSize)
    
    for city in cities:
        # 대소문자 구분을 안 하므로 무조건 소문자로 통일
        city = city.lower()
        
        # 2. 캐시 히트 (바구니에 이미 있는 경우)
        if city in cache:
            answer += 1
            cache.remove(city) # 순서 갱신을 위해 지우고
            cache.append(city) # 맨 뒤로 새로 장착
            
        # 3. 캐시 미스 (바구니에 없는 경우)
        else:
            answer += 5
            cache.append(city) # 넣는 순간 maxlen 덕분에 맨 앞은 자동 탈락
            
    return answer
```