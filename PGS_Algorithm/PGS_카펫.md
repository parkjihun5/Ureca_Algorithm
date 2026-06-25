### PGS 카펫 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/42842

```python
def solution(brown, yellow):
    # 1. 카펫의 전체 격자 개수를 구함
    total = brown + yellow
    
    # 2. 세로 길이(h)를 3부터 시작해서 전체 격자 수까지 1씩 늘리며 탐색
    # 세로가 최소 3이어야 위/아래 갈색 테두리를 빼고 가운데 노란색이 채워질 공간이 생김
    for h in range(3, total + 1):
        
        # 3. 전체 격자 수(total)가 현재 세로 길이(h)로 깔끔하게 나누어떨어지는지 확인
        # 나누어떨어진다는 것은 'h'가 전체 격자 수의 진짜 '약수'라는 뜻
        if total % h == 0:
            # 약수가 맞다면, 짝꿍인 가로 길이(w)를 계산
            w = total // h
            
            # 가로(w)는 세로(h)보다 크거나 같아야 한다는 문제 조건 방어벽
            if w >= h:
                
                # 4. [핵심 조건 검사] 테두리(2칸씩)를 뺀 내부 노란색의 면적이 
                # 실제 입력으로 받은 yellow 개수와 완벽하게 일치하는지 확인
                if (w - 2) * (h - 2) == yellow:
                    # 일치한다면 이 가로, 세로 쌍이 진짜 정답이므로 즉시 리턴하고 종료
                    return [w, h]
```