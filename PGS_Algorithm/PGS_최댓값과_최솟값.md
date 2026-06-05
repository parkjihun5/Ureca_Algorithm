### PGS 최댓값과 최솟값 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12939

```python
def solution(s):
    
    num_lst = list(map(int, s.split()))
    
    max_val = max(num_lst)
    min_val = min(num_lst)
    
    answer = (f"{min_val} {max_val}")
    return answer
```