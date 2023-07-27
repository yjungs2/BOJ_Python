- 230109
## 백준 > Bronze2 > 1225번 : 이상한 곱셈
(2) 메모리 30616kb 시간 48ms  
https://www.acmicpc.net/problem/1225  

```
(1) a * d + b * d + c * d  
(2) (a + b + c) * d
```

코드 (1)
```python
# 시간초과 (이중for문 사용)
a, b = input().split()
ans = 0
for i in a:
  for j in b:
    ans += int(i)*int(j)
print(ans)
```

코드 (2)
```python
# for문 2번 사용
a, b = input().split()
ans = 0
suma = 0
for i in a:
  suma += int(i)
for j in b:
  ans += suma * int(j)
print(ans)
```

입력
```
123 45
```

출력
```
54
```