### PGS 짝지어 제거하기 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12973

```python
def solution(s):
    stack = []

    for char in s:
        # 1. 바구니에 글자가 들어있고, 맨 위에 있는 글자가 지금 넣으려는 글자와 같다면?
        if stack and stack[-1] == char:
            stack.pop()  # 바구니 맨 위 글자를 터뜨려서 제거 (인덱스 없이 쓰면 맨 뒤를 뺌)
        else:
            stack.append(char)  # 중복이 아니면 바구니에 차곡차곡 쌓음

    # 바구니에 남은 글자들을 다시 문자열로 합치기
    if len(stack) == 0:
        answer = 1
    else:
        answer = 0
    return answer
```