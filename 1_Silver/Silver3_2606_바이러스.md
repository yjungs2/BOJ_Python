- 230105
## 백준 > Silver3 > 2606번 : 바이러스
메모리 30616kb 시간 40ms  
https://www.acmicpc.net/problem/2606  

코드
```python
n = int(input()) # 컴퓨터의 수 n (1번 ~ n번)
graph = [[] for _ in range(n+1)] # 연결된 컴퓨터 담을 배열
net = int(input()) # 연결되어 있는 컴퓨터 쌍의 수
for _ in range(net):
  a, b = map(int, input().split())
  graph[a].append(b) # a 컴퓨터에 b가 연결되어 있음
  graph[b].append(a) # b 컴퓨터에 a가 연결되어 있음
ans = 0 # 1번 컴퓨터를 통해 바이러스에 걸리게 되는 컴퓨터의 수
visited = [0]*(n+1) # 방문 정보 표시할 리스트
def dfs(i): # DFS 함수 정의
  global ans # 전역변수 사용
  visited[i] = 1 # 방문 표시
  for j in graph[i]: # 연결된 컴퓨터 중에서
    if visited[j] == 0: # 방문한 적이 없으면
      dfs(j) # 함수 호출
      ans += 1 # 바이러스 컴퓨터 수 증가
dfs(1)
print(ans)
```

입력
```
7
6
1 2
2 3
1 5
5 2
5 6
4 7
```

출력
```
4 # 2, 3, 5, 6
```