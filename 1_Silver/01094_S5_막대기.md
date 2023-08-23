- 221110
## 백준 > Silver5 > 1094번 : 막대기
메모리 30840kb 시간 80ms  
https://www.acmicpc.net/problem/1094  

예시
```
23 = 16 + 4 + 2 + 1 -> 4개    
32 = 32 -> 1개  
64 = 64 -> 1개  
48 = 32 + 16 -> 2개
```

코드
```python
x = int(input())
sticks = [64, 32, 16, 8, 4, 2, 1, 1]
cnt = 0
for s in sticks:
    if x==0:
        break
    else:
        if x>=s:
            x = x-s
            cnt+=1
print(cnt)
```

입력
```
23

32

64

48
```

출력
```
4

1

1

2
```