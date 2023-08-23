- 221124
## 백준 > Silver4 > 1764번 : 듣보잡
(1) 메모리 42108kb 시간 5368ms  
(2) 메모리 42108kb 시간 128ms  
https://www.acmicpc.net/problem/1764  

```
'리스트'를 사용하니 결과가 시간초과가 되어서  
순서가 필요없는 '듣도 못한 사람의 명단', '보도 못한 사람의 명단'은 '집합'을 사용했다.  
```

코드 (1)
```python
# set 사용 - 시간복잡도 고려
n, m = map(int, input().split(" "))
nohear = set()
nosee = set()
for _ in range(n):
    nohear.add(input()) # 듣도 못한 사람의 명단
for _ in range(m):
    nosee.add(input()) # 보도 못한 사람의 명단
nohs = []
if n<m: # 듣도 못한 사람의 수가 적다면
    for i in nohear: # 그 중에서
        if i in nosee: # 보도 못한 사람의 명단에 속한다면
            nohs.append(i) # 듣보잡 명단에 추가
else: # 보도 못한 사람의 수가 적다면
    for j in nosee: # 그 중에서
        if j in nohear: # 듣도 못한 사람의 명단에 속한다면
            nohs.append(j) # 듣보잡 명단에 추가
nohs.sort() # 사전순 정렬
print(len(nohs))
for k in range(len(nohs)):
    print(nohs[k])
```

```
(1)에 더해 sys.stdin.readline으로 입력받기.  
사람의 명단을 n, m개의 줄에 걸쳐 입력받기 때문에 실행시간을 고려하여 변경했다.  
이름을 입력받을 때 **strip()**을 꼭 붙여줘야 한다!
```

코드 (2)
```python
import sys
input = sys.stdin.readline # readline으로 입력받기

n, m = map(int, input().split())
nohear = set()
nosee = set()
for _ in range(n):
    nohear.add(input().strip()) # 듣도 못한 사람의 명단
for _ in range(m):
    nosee.add(input().strip()) # 보도 못한 사람의 명단
nohs = []
if n<m: # 듣도 못한 사람의 수가 적다면
    for i in nohear: # 그 중에서
        if i in nosee: # 보도 못한 사람의 명단에 속한다면
            nohs.append(i) # 듣보잡 명단에 추가 
else: # 보도 못한 사람의 수가 적다면
    for j in nosee: # 그 중에서
        if j in nohear: # 듣도 못한 사람의 명단에 속한다면
            nohs.append(j) # 듣보잡 명단에 추가
nohs.sort() # 사전순 정렬
print(len(nohs))
for k in range(len(nohs)):
    print(nohs[k])
```

입력
```
3 4  
ohhenrie  
charlie  
baesangwook  
obama  
baesangwook  
ohhenrie  
clinton
```

출력
```
2  
baesangwook  
ohhenrie
```