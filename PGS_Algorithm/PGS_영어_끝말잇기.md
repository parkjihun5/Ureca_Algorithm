### PGS 영어 끝말잇기 문제 풀이
https://school.programmers.co.kr/learn/courses/30/lessons/12981

```python
def solution(n, words):
    # 이미 나온 단어들을 기억해 둘 바구니 (중복 검사용)
    used_words = set()
    
    for i in range(len(words)):
        word = words[i]  # 현재 단어
        
        # [탈락 조건 1] 이미 말했던 단어를 또 말했을 때
        if word in used_words:
            return [(i % n) + 1, (i // n) + 1]
            
        # [탈락 조건 2] 첫 번째 단어가 아닌데, 앞 단어의 끝 글자로 시작하지 않을 때
        if i > 0 and words[i-1][-1] != word[0]:
            return [(i % n) + 1, (i // n) + 1]
            
        # 탈락 조건을 모두 무사히 통과했다면 바구니에 현재 단어 저장
        used_words.add(word)
        
    # 만약 탈락자가 아무도 없이 게임이 끝났다면 [0, 0] 리턴
    return [0, 0]
```