- 220611
##  백준 > Bronze2 > 2292번 : 벌집
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/2292  

아이디어
```
if n == 1:
    print(1)
elif 2 <= n <= 7: # 6
    print(2)
elif 8 <= n <= 19: # 12
    print(3)
elif 20 <= n <= 37: # 18
    print(4)
elif 38 <= n <= 61: # 24
    print(5)
elif
...
이런 식으로 결과가 나와야 한다.
조건에서 n이 1부터 1,000,000,000까지 이므로 이 방법 말고 식으로 해야 한다.
nlist = [1, 6*1, 6*2, 6*3, 6*4, ...]
nsum = 1 + 6*1 + 6*2 + 6*3 + 6*4 + ... 이 되도록 짰다.
```

코드
```python
n = int(input())
nlist = [1]
nsum = 1
i = 1
while True:
    if n <= nsum: # n이 1일 때 1을 출력하려면 while문 앞에 와야 함
        break
    nlist.append(6*i) # nlist = [1, 6*1, 6*2, 6*3, 6*4, ...]
    nsum += 6*i # nsum = 1 + 6*1 + 6*2 + 6*3 + 6*4 + ...
    i += 1
print(i)
```

입력
```
13

70
```

출력
```
3

6
```