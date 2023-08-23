- 221122
## 백준 > Silver4 > 1920번 : 수 찾기
(2) 메모리 51368kb 시간 192ms  
https://www.acmicpc.net/problem/1920  

코드 (1) - 시간 초과
```python
# 시간 초과
n = int(input())
nlist = list(map(int, input().split(' ')))
nlist.sort()
nmax = nlist[n-1]
m = int(input())
mlist = list(map(int, input().split(' ')))
mlist.sort()
mmax = mlist[m-1]

for i in range(m):
    if mlist[i] > nmax:
        print(0)
    else:
        if mlist[i] in nlist:
            print(1)
        else:
            print(0)
```

해결 방법
```
n개의 수랑 m개의 수를 모두 list에 담으니 시간초과가 났지만,  
순서가 필요없는 n개의 수를 set에 담고,  
순서가 필요한 m개의 수를 list에 담으니 시간초과가 나지 않았다.
```

코드 (2) - 성공
```python
n = int(input())
nlist = list(map(int, input().split())) # n개의 정수
nset = set(nlist) # 순서가 필요없으므로 set에 담기
m = int(input())
mlist = list(map(int, input().split())) # m개의 정수

for i in mlist: # m개의 수들이 각각
    if i in nset: # n개의 수 집합 안에 존재하면
        print(1) # 1 출력
    else: # 존재하지 않으면
        print(0) # 0 출력
```

입력
```
5  
4 1 5 2 3  
5  
1 3 7 9 5
```

출력
```
1  
1  
0  
0  
1
```