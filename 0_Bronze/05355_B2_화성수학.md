- 230127
## 백준 > Bronze2 > 5355번 : 화성 수학
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/5355  

코드
```python
t = int(input()) # 테스트 케이스 개수
for _ in range(t):
  ope = list(input().split()) # 화성 수학식 리스트
  ans = float(ope[0]) # 수
  for i in range(1, len(ope)): # 연산자 계산
    if ope[i] == "@":
      ans *= 3
    elif ope[i] == "%":
      ans += 5
    elif ope[i] == "#":
      ans -= 7
  print(f'{ans:.2f}') # 소수점 둘째 자리까지 출력
```

입력
```
3
3 @ %
10.4 # % @
8 #
```

출력
```
14.00
25.20
1.00
```