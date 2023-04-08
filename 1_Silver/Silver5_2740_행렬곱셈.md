- 221109
## 백준 > Silver5 > 2740번 : 행렬 곱셈
메모리 30840kb 시간 244ms  
https://www.acmicpc.net/problem/2740  

코드
```python
n, m = map(int, input().split(" "))
mata = [[0]*m for _ in range(n)] # 크기가 n*m인 행렬 mata
for i in range(n):
    mata[i] = list(map(int, input().split(" ")))
m, k = map(int, input().split(" "))
matb = [[0]*k for _ in range(m)] # 크기가 m*k인 행렬 matb
for j in range(m):
    matb[j] = list(map(int, input().split(" ")))
ans = [[0]*k for _ in range(n)] # 두 행렬의 곱을 담을 행렬 ans
for x in range(n):
    for y in range(k):
        mul = 0
        for z in range(m):
            mul += mata[x][z]*matb[z][y]
        ans[x][y] = mul
for a in range(n):
    for b in range(k):
        print(ans[a][b], end=" ")
    print(end="\n")
```

입력
```
3 2
1 2
3 4
5 6
2 3
-1 -2 0
0 0 3
```

출력
```
-1 -2 6
-3 -6 12
-5 -10 18
```