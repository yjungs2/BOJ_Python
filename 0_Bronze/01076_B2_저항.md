- 220630
##  백준 > Bronze2 > 1076번 : 저항
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/1076  

코드
```python
color = ['black', 'brown', 'red', 'orange', 'yellow', 'green', 'blue', 'violet', 'grey', 'white']
c1 = input() # 첫 번째 색
for i in range(10):
    if color[i] == c1:
        n1 = i # 첫 번째 값
c2 = input() # 두 번째 색
for i in range(10):
    if color[i] == c2:
        n2 = i # 두 번째 값
c3 = input() # 세 번째 색
for i in range(10):
    if color[i] == c3:
        n3 = 10 ** i # 세 번째 곱
print((10 * n1 + n2) * n3) # 저항의 값
```

입력
```
yellow
violet
red

white
white
white
```

출력
```
4700

99000000000
```