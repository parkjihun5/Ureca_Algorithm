### PGS N개의 최소공배수 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12953

```python
import math

def solution(arr):
    # 1. 처음 기준이 될 최소공배수(LCM)를 리스트의 첫 번째 값으로 설정
    current_lcm = arr[0]
    
    # 2. 두 번째 숫자부터 차례대로 꺼내며 눈을 굴림
    for i in range(1, len(arr)):
        next_num = arr[i]
        
        # 3. 두 수의 곱 // 두 수의 최대공약수
        # math.gcd가 최대공약수를 알아서 계산
        current_lcm = (current_lcm * next_num) // math.gcd(current_lcm, next_num)
        
    return current_lcm
```