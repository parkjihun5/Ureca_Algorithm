### PGS 피보나치 수 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12945

```
def solution(n):
    answer = 0

    fibo = [0, 1] # 피보나치 수의 0번과 1번은 0과 1로 고정

    if n >= 2:
        for i in range(1, n):
            num = fibo[-1] + fibo[-2] # 반복문을 통해 피보나치 수를 구함
            fibo.append(num) # 피보나치 수의 수들을 리스트에 저장

        answer = fibo[-1] % 1234567 # 마지막 수를 1234567로 나누고 남은 나머지를 답으로 저장
    
    elif n == 1:
        print(fibo[1]) # n이 2보다 작을 경우 0 또는 1을 출력
    else:
        print(fibo[0])

    return answer
```