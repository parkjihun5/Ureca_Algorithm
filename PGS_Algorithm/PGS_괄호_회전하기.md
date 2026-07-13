### PGS 괄호 회전하기 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/76502

```python
def solution(s):
    answer = 0

    pair = {
        "}" : "{",
        "]" : "[",
        ")" : "("
    }

    for n in range(len(s)):
        s1 = s[n:] + s[:n]
        stack = []
        is_valid = True # 이번 회전 모양이 진짜 정답인지 체크할 깃발

        for i in s1:
            # 1. 여는 괄호는 안전하게 스택에 담기
            if i not in pair:
                stack.append(i)

            # 2. 닫는 괄호를 만났을 때
            if i in pair:
                # 방어벽: 스택이 비어있거나, 맨 위 짝꿍이 내 열쇠와 안 맞으면 탈락
                if not stack or stack[-1] != pair[i]:
                    is_valid = False
                    break # 이미 틀렸으니 이 바퀴(s1)는 더 검사할 필요도 없이 탈출
                else:
                    stack.pop() # 짝이 맞았으니 다음 검사를 위해 스택 맨 위를 제거

        # 3. 6글자 다 돌았는데 깃발도 True이고, 남은 자물쇠도 없다면(not stack) 진짜 올바른 괄호 세트 세기
        if is_valid and not stack:
            answer += 1
    return answer
```