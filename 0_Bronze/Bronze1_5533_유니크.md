- 230110
## 백준 > Bronze1 > 5533번 : 유니크
메모리 30616kb 시간 44ms  
https://www.acmicpc.net/problem/5533  

코드
```python
n = int(input()) # 참가자의 수 n
player = [[0]*3 for _ in range(n)]
for i in range(n):
  player[i] = list(map(int, input().split())) # 참가자가 쓴 수 배열에 담기
first, second, third = [], [], []
for i in range(n):
  first.append(player[i][0]) # 첫 번째 게임에서 쓰인 수들
  second.append(player[i][1]) # 두 번째 게임에서 쓰인 수들
  third.append(player[i][2]) # 세 번째 게임에서 쓰인 수들
for j in range(n): # 각 플레이어의
  score = 0 # 점수 리셋
  if first.count(player[j][0]) == 1: # 자신과 같은 수를 쓴 사람이 없으면
    score += player[j][0] # 첫 번째 게임 점수 얻기
  if second.count(player[j][1]) == 1:
    score += player[j][1] # 두 번째 게임 점수 얻기
  if third.count(player[j][2]) == 1:
    score += player[j][2] # 세 번째 게임 점수 얻기
  print(score) # 점수 출력
```

입력
```
5
100 99 98
100 97 92
63 89 63
99 99 99
89 97 98

3
89 92 77
89 92 63
89 63 77
```

출력
```
0
92
215
198
89

0
63
63
```