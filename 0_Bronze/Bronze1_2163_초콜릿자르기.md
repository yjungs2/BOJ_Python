- 221106
##  백준 > Bronze1 > 2163번 : 초콜릿 자르기
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/2163  

예시
```
3x2 초콜릿 -> 최소 5번
4x2 초콜릿 -> 최소 7번
3x3 초콜릿 -> 최소 8번
```

코드
```python
n, m = map(int, input().split(" "))
print(n*m-1)
```

입력
```
2 2

1 1
```

출력
```
3

0
```