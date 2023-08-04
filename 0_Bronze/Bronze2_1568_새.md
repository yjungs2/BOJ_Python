- 230206
##  백준 > Bronze2 > 1568번 : 새
메모리 31256kb 시간 52ms  
https://www.acmicpc.net/problem/1568  

코드
```python
n = int(input()) # 새의 수
ans = 0
sing = 1
while(n): # 앉아있는 새가 있다면
  ans += 1 # 1초 추가
  if n < sing: # 나무에 앉아있는 새의 수가 지금 불러야 하는 수보다 작다면
    sing = 1 # 1부터 시작
  n -= sing # 숫자만큼 날아간 새
  sing += 1 # 불러야 하는 수 증가
print(ans) # 모든 새가 날아가기까지 총 걸리는 초 출력
```

입력
```
1

3

4

14

100
```

출력
```
1

2

3

7

18
```