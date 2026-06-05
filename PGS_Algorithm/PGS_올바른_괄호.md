### PGS 올바른 괄호 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12909

```python
def solution(s):
    balance = 0
    
    for char in s:
        if char == '(':
            balance += 1
        else: # ')'인 경우
            balance -= 1
        
        # 중간에 밸런스가 깨지면 (닫는 괄호가 더 많아지면) 즉시 종료
        if balance < 0:
            return False
            
    # 모든 검사 후 0이면 성공, 아니면(여는 괄호가 남으면) 실패
    return balance == 0
```