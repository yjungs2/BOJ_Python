- 230124
## 백준 > Bronze2 > 1668번 : 트로피 진열
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/1668  

코드
```python
n = int(input()) # 트로피 개수 n
trp = []
for _ in range(n):
  trp.append(int(input())) # 트로피 리스트
left, right = 1, 1 # 양편에서 보이는 트로피 개수 기본 1개 지정
for i in range(1, n): # 왼쪽에서 2번째부터
  if trp[i] > max(trp[:i]): # 해당 트로피가 왼쪽 트로피들의 최대 높이보다 크다면
    left += 1 # 보이는 개수 +1
for j in range(n-2, -1, -1): # 오른쪽에서 2번째부터
  if trp[j] > max(trp[j+1:]): # 해당 트로피가 오른쪽 트로피들의 최대 높이보다 크다면
    right += 1 # 보이는 개수 +1
print(left) # 왼쪽에서 보이는 트로피 개수 출력
print(right) # 오른쪽에서 보이는 트로피 개수 출력
```

입력
```
7
1
4
2
5
3
7
1
```

출력
```
4
2
```