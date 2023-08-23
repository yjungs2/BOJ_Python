- 221101
## 백준 > Silver4 > 11399번 : ATM
메모리 30840kb 시간68ms  
https://www.acmicpc.net/problem/11399  

코드
```python
n = int(input()) # 사람 n명
nlist = list(map(int, input().split(" "))) # 인출에 걸리는 시간
nlist.sort() # 시간 오름차순 정렬
plist = [] # 누적 시간
psum = 0
for i in range(n):
  if i == 0:
    plist.append(nlist[i])
    psum += plist[i]
  else:
    plist.append(nlist[i]+plist[i-1]) # 누적 시간 계산
    psum += plist[i]
print(psum) # 누적 시간 전체 합
```

입력
```
5
3 1 4 3 2
```

출력
```
32
```