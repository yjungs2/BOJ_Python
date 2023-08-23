- 221031
## 백준 > Silver3 > 2193번 : 이친수
메모리 30840kb 시간80ms  
https://www.acmicpc.net/problem/2193  

코드
```python
n = int(input())
nlist = [0]*91
nlist[1] = 1
nlist[2] = 1
for i in range(3,n+1):
    nlist[i] = nlist[i-1] + nlist[i-2] # 피보나치 수열과 같음
print(nlist[n])
```

입력
```
3

10
```

출력
```
2

55
```