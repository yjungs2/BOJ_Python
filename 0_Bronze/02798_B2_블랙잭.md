- 221103
## 백준 > Bronze2 > 2798번 : 블랙잭
메모리 30840kb 시간112ms  
https://www.acmicpc.net/problem/2798  

코드 (1) - 시간 초과
```python
# 시간 초과
from itertools import combinations
n, m = map(int, input().split(' ')) # 카드 개수 n, 합 m
cards = list(map(int, input().split(' '))) # 카드에 쓰여 있는 양의 정수들
comcards = list(combinations(cards, 3)) # 카드 3개를 선택하는 조합
# print(comcards)
sumcards = [] # 선택한 카드 3개의 합 넣을 리스트
for i in range(len(comcards)):
    if sum(comcards[i]) not in sumcards: # 중복되지 않으면
        sumcards.append(sum(comcards[i])) # 리스트에 추가
sumcards.sort() # 오름차순 정렬
# print(sumcards)
answer = 0
for k in sumcards:
    if k <= m:
        answer = k
print(answer)
```

코드 (2) - 성공
```python
n, m = map(int, input().split(" "))
nlist = list(map(int, input().split(" ")))
nlist.sort()
#print(nlist)
sumn = 0
smax = 0
for i in range(n):
    for j in range(i+1, n):
        for k in range(j+1, n):
            sumn = nlist[i]+nlist[j]+nlist[k]
            if sumn > m:
                break
            elif sumn <= m and sumn > smax:
                smax = sumn
print(smax)
```

입력
```
10 500
93 181 245 214 315 36 185 138 216 295
```

출력
```
497
```