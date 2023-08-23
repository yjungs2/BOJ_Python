- 230114
## 백준 > Bronze1 > 2851번 : 슈퍼 마리오
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/2851  

코드
```python
nums = []
for _ in range(10): # 10개의 정수 입력
  nums.append(int(input())) # 리스트에 추가
ans = 0
for i in range(10): # 처음나온 순서대로
  ans += nums[i] # 버섯을 먹고 점수 획득
  if ans == 100: # 점수가 100이라면
    print(ans) # 출력
    break
  elif ans > 100: # 점수가 100보다 크다면
    if abs(ans - 100) > abs(100 - (ans-nums[i])): # 100 미만의 점수가 100에 가까우므로
      print(ans-nums[i]) # 작은 값 출력
      break
    elif abs(ans - 100) == abs(100 - (ans-nums[i])): # 가까운 수가 2개이므로
      print(ans) # 큰 값 출력
      break
    else: # 100 이상의 점수가 100에 가까우므로
      print(ans) # 큰 값 출력
      break
if ans < 100: # 반례 추가 (10개 합 점수가 100보다 작다면)
  print(ans) # 해당 값 출력
```

입력
```
10
20
30
40
50
60
70
80
90
100

1
2
3
5
8
13
21
34
55
89

40
40
40
40
40
40
40
40
40
40

0
0
0
0
0
0
0
0
0
1
```

출력
```
100

87

120 # (80, 120) 중 큰 값 선택

1
```