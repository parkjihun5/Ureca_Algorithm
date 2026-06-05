### PGS 이진 변환 반복하기 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/70129

```python
def solution(s):
    loop_count = 0  # 이진 변환 횟수 (while문이 돈 횟수)
    zero_count = 0  # 제거된 모든 0의 개수 누적
    
    # s가 "1"이 될 때까지 계속 반복합니다.
    while s != "1":
        loop_count += 1  # 라운드 시작했으니 1 증가
        
        # 1. 이번 라운드에서 제거될 '0'의 개수를 세어서 누적합니다.
        zero_count += s.count('0')
        
        # 2. '0'을 완전히 제거하고 남은 '1'들만 챙깁니다.
        s = s.replace('0', '')
        
        # 3. 남은 '1'들의 길이를 구합니다.
        length = len(s)
        
        # 4. 그 길이를 이진법 문자열로 바꿔서 s에 다시 대입합니다.
        s = bin(length)[2:]
        
    # [이진 변환 횟수, 제거된 0의 개수] 형태로 반환합니다.
    return [loop_count, zero_count]
```