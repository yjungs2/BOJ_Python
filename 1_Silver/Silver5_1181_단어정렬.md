- 220717
## 백준 > Silver5 > 1181번 : 단어 정렬
메모리 32884kb 시간 4572ms  
https://www.acmicpc.net/problem/1181  

코드
```python
n = int(input()) # 단어의 개수
wordlist = [] # 단어를 담을 리스트
long = 0
for i in range(n):
    word = input()
    if word not in wordlist: # 중복되지 않으면
        wordlist.append(word) # 리스트에 단어 추가
    long = max(len(word), long) # 단어의 길이 최대값 업데이트
wordlist.sort() # 오름차순 정렬
for j in range(1, long+1): # 단어의 길이가 1부터 최대값까지
    for k in wordlist: # 리스트 안을 돌면서
        if len(k) == j: # 길이가 작은 것부터 출력
            print(k)
```

입력
```
13
but
i
wont
hesitate
no
more
no
more
it
cannot
wait
im
yours
```

출력
```
i
im
it
no
but
more
wait
wont
yours
cannot
hesitate
```