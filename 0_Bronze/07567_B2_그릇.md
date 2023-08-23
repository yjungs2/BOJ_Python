- 230129
##  백준 > Bronze2 > 7567번 : 그릇
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/7567  

```
그릇을 바닥에 놓았을 때 그 높이는 10cm  
두 개의 그릇을 같은 방향으로 포개면 그 높이는 5cm
```

코드
```python
dish = input() # 입력된 괄호 문자열
ans = 10 # 처음 그릇 높이
for i in range(1, len(dish)):
  if dish[i] == dish[i-1]: # 앞의 그릇과 같은 방향이면
    ans += 5 # 포개져서 높이 5 추가
  else: # 다른 방향이면
    ans += 10 # 그릇 높이만큼 10 추가
print(ans)
```

입력
```
((((

()()()))(
```

출력
```
25

80
```