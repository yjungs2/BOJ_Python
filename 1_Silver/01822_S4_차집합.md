- 221231
## 백준 > Silver4 > 1822번 : 차집합
메모리 112344kb 시간 916ms  
https://www.acmicpc.net/problem/1822  

코드
```python
asize, bsize = map(int, input().split()) # 집합 A와 집합 B의 크기
ali = list(map(int, input().split())) # 집합 A의 원소 리스트
bli = list(map(int, input().split())) # 집합 B의 원소 리스트
bset = set(bli) # 집합 B
ansli = []
ali.sort()
for i in ali: # 집합 A에 속하면서
  if i not in bset: # 집합 B에 속하지 않는 원소를
    ansli.append(i) # 정답 리스트에 추가
if ansli == 0: # 없다면
  print(0)
else: # 있다면
  print(len(ansli)) # 개수 출력
  for j in ansli:
    print(j, end=" ") # 구체적인 원소를 증가하는 순서로 출력
```

입력
```
4 3
2 5 11 7
9 7 4

3 5
2 5 4
1 2 3 4 5
```

출력
```
3
2 5 11

0
```