- 221102
## 백준 > Silver5 > 7568번 : 덩치
메모리 30840kb 시간68ms  
https://www.acmicpc.net/problem/7568  

코드
```python
n = int(input()) # 전체 사람 수
xlist = []
ylist = []
for i in range(n):
    x, y = map(int, input().split(" ")) # 몸무게 x, 키 y
    xlist.append(x)
    ylist.append(y)
for i in range(n):
    rank = 1 # rank는 count + 1 해야하므로
    for j in range(n):
        if xlist[i] < xlist[j] and ylist[i] < ylist[j]: # 나보다 몸무게와 키 모두 큰 사람
            rank += 1 # 수만큼 증가
    print(rank, end=" ")
```

입력
```
5
55 185
58 183
88 186
60 175
46 155
```

출력
```
2 2 1 2 5
```