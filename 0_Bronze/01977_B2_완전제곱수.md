- 220613
##  백준 > Bronze2 > 1977번 : 완전제곱수
메모리 30840kb 시간 72ms  
https://www.acmicpc.net/problem/1977  

코드
```python
m = int(input())
n = int(input())
pn = []
pnsum = 0
for i in range(m, n+1): # m 이상 n 이하 자연수 i
    if (i ** 0.5 ) % 1 == 0: # i가 완전제곱수이면
        pn.append(i)
        pnsum += i
if len(pn) == 0: # 완전제곱수 없으면
    print(-1) # -1 출력
else:
    print(pnsum) # 완전제곱수의 합
    print(pn[0]) # 완전제곱수 중 최솟값
```

입력
```
60
100

75
80
```

출력
```
245
64

-1
```