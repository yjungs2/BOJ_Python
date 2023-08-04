- 230209
##  백준 > Silver3 > 9461번 : 파도반 수열
메모리 31256kb 시간 48ms  
https://www.acmicpc.net/problem/9461  

코드
```python
p = [1, 1, 1, 2, 2, 3, 4, 5, 7, 9] # 파도반 수열 P(N)
t = int(input()) # 테스트 케이스 개수 t
for i in range(t):
  n = int(input())
  if n > len(p): # 입력값이 저장된 수열 번호보다 크다면
    for j in range(len(p), n):
      p.append(p[j-3] + p[j-2]) # 수열 규칙대로 추가하기
  print(p[n-1]) # P(입력) 출력
```

입력
```
2
6
12
```

출력
```
3
16
```