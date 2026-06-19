### PGS 귤 고르기 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/138476

```python
from collections import Counter

def solution(k, tangerine):

    count_map = Counter(tangerine)
    
    counts = sorted(count_map.values(), reverse=True)
    
    answer = 0  
    total = 0   
    
    for count in counts:
        total += count
        answer += 1 
        
        if total >= k:
            break
            
    return answer
```