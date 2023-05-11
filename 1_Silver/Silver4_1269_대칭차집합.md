- 221201
## 백준 > Silver4 > 1269번 : 대칭 차집합
메모리 77356kb 시간 288ms  
https://www.acmicpc.net/problem/1269  

코드
```python
a, b = map(int, input().split()) # 집합 A, B의 원소의 개수
lia, lib = [], []
lia = list(map(int, input().split())) # 리스트 A
lib = list(map(int, input().split())) # 리스트 B
seta = set(lia) # 집합 A
setb = set(lib) # 집합 B
ans = 0
for i in lia:
  if i not in setb:
    ans += 1 # 차집합 A-B 원소의 개수 더하기
for j in lib:
  if j not in seta:
    ans += 1 # 차집합 B-A 원소의 개수 더하기
print(ans) # 대칭 차집합의 원소의 개수 출력
```

입력
```
3 5  
1 2 4  
2 3 4 5 6  
```

출력
```
4
```