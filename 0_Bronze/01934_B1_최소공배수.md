- 221203
## 백준 > Bronze1 > 1934번 : 최소공배수
메모리 30840kb 시간 164ms  
https://www.acmicpc.net/problem/1934  

코드
```python
t = int(input()) # 테스트 케이스 개수
def gcd(a, b): # 최대공약수 함수 정의
  if a%b == 0:
    return b
  else:
    return gcd(b, a%b)
for _ in range(t):
  nums = list(map(int, input().split()))
  a = max(nums) # 두 자연수 중 큰 수
  b = min(nums) # 두 자연수 중 작은 수
  print(a*b//gcd(a, b)) # 최소공배수 출력
```

입력
```
3  
1 45000  
6 10  
13 17
```

출력
```
45000  
30  
221
```