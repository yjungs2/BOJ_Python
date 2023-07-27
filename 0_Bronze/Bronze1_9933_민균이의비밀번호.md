- 230108
## 백준 > Bronze1 > 9933번 : 민균이의 비밀번호
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/9933  

코드
```python
n = int(input()) # 단어의 수
words = set() # 단어 담을 집합 (효율성 위해 리스트 말고 집합 선택)
pw = ""
for _ in range(n):
  word = input()
  words.add(word)
  if word[::-1] == word or word[::-1] in words: # 팰린드롬이거나 뒤집은 글자가 집합에 존재하면
    pw = word # 해당 단어가 비밀번호
print(len(pw), pw[(len(pw)-1)//2]) # 비밀번호의 길이와 가운데 글자 출력
```

입력
```
4
las
god
psala
sal

4
kisik
ptq
tttrp
tulipan
```

출력
```
3 a

5 s
```