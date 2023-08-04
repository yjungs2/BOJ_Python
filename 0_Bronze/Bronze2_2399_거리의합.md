- 230203
##  백준 > Bronze2 > 2399번 : 거리의 합
PyPy3 메모리 115296kb 시간 472ms  
https://www.acmicpc.net/problem/2399  

코드
```python
n = int(input())
nums = list(map(int, input().split()))
ans = 0
for i in range(0, n-1): # 서로 다른 두 좌표 사이의
  for j in range(i+1, n):
    ans += abs(nums[i] - nums[j]) # 거리 더하기
print(2*ans) # n^2 쌍이므로 계산한 거리*2 출력
```

입력
```
5
1 5 3 2 4
```

출력
```
40
# (4+2+1+3+2+3+1+1+1+2)*2
```