- 221130
## 백준 > Silver5 > 5800번 : 성적 통계
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/5800  

코드
```python
k = int(input()) # 반의 수
classx = []
xnum = 0
scores = []
for i in range(1, k+1): # 반마다 돌면서
  classx = list(map(int, input().split()))
  xnum = classx[0] # 각 반의 학생 수
  scores = classx[1:] # 학생들의 수학 성적
  scores.sort(reverse=True) # 성적 내림차순 정렬
  sgap = 0
  for j in range(1, xnum):
    sgap = max(sgap, scores[j-1] - scores[j]) # 가장 큰 인접한 점수 차이 갱신
  print(f"Class {i}") # 반 번호 출력
  print(f"Max {max(scores)}, Min {min(scores)}, Largest gap {sgap}") # 가장 높은 점수, 낮은 점수, 큰 인접 점수 차 출력
```

입력
```
2  
5 30 25 76 23 78  
6 25 50 70 99 70 90
```

출력
```
Class 1  
Max 78, Min 23, Largest gap 46  
Class 2  
Max 99, Min 25, Largest gap 25
```