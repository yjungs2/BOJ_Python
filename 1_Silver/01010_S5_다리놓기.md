- 220716
## 백준 > Silver5 > 1010번 : 다리 놓기
메모리 30840kb 시간 112ms  
https://www.acmicpc.net/problem/1010  

combinations 조합 라이브러리 사용  
코드 (시간초과)
```python
# Python3 시간 초과
# PyPy3 메모리 초과
from itertools import combinations

t = int(input())
for i in range(t):
    n, m = map(int, input().split(' '))
    nm = combinations(range(m), n)
    print(len(list(nm)))
```

```
조합 라이브러리를 쓰면 시간 초과가 나서 조합 식을 그대로 풀어서 계산하는 방식으로 코드를 짰다.
```

코드
```python
t = int(input())
for i in range(t):
    n, m = map(int, input().split(' '))
    n = min(n, m-n) # 5C2 = 5C3 이지만 5C2의 계산이 더 간단하므로 n에 반영
    pnum = 1
    cnum = 1
    for p in range(m, m-n, -1): # m * (m-1) * ... * (m-n+1)
        pnum *= p
    for c in range(n, 0, -1): # n * (n-1) * ... * 1
        cnum *= c
    print(round(pnum/cnum))
    # round를 안 쓰면 소수점까지 출력해서 사용함
    # 꼭 나누어떨어지는 수이므로 반올림 걱정할 필요 없음
```

입력
```
3
2 2
1 5
13 29
```

출력
```
1
5
67863915
```