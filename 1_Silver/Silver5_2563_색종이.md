- 221107
## 백준 > Silver5 > 2563번 : 색종이
메모리 30840kb 시간 72ms  
https://www.acmicpc.net/problem/2563  

아이디어
```
(각 색종이 넓이) - (겹치는 부분들 넓이)는 계산이 어려우므로  
가로x세로 100x100이 주어져 있으므로 그 안에서 검은 영역을 세기.  
각 영역의 크기는 1x1이므로 1이다.
```

코드
```python
rec = [[0]*100 for _ in range(100)] # 가로 세로 크기가 각각 100인 흰색 도화지
n = int(input()) # 색종이 개수
for i in range(n):
    x, y = map(int, input().split(" ")) # 시작 좌표 x, y
    for a in range(x-1, x+9):
        for b in range(y-1, y+9):
            rec[a][b] = 1 # 색종이 영역 값을 1로 바꾸기
ans = 0
for j in range(100):
    ans += sum(rec[j]) # 색종이 영역 더하기
print(ans)
```

입력
```
3
3 7
15 7
5 2
```

출력
```
260
```