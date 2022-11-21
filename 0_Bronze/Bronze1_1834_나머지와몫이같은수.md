- 220722
## 백준 > Bronze1 > 1834번 : 나머지와 몫이 같은 수
메모리 30840kb 시간436ms  
https://www.acmicpc.net/problem/1834  

코드
```python
n = int(input())
total = 0
for i in range(1, n): # 1부터 (n-1)까지
    total += (n * i + i)
print(total)
```

입력
```
3

2000000
```

출력
```
12

3999999999999000000
```