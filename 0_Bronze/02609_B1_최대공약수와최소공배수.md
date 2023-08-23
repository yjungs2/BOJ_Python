- 221202
## 백준 > Bronze1 > 2609번 : 최대공약수와 최소공배수
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/2609  

코드
```python
nums = list(map(int, input().split())) # 두 개의 자연수 입력받음
a = max(nums) # 두 수 중 큰 수
b = min(nums) # 두 수 중 작은 수
def gcd(a, b): # 최대공약수 함수 정의
  if a%b == 0:
    return b
  else:
    return gcd(b, a%b)
print(gcd(a, b)) # 최대공약수 출력
print(a*b//gcd(a,b)) # 최소공배수 출력
```

입력
```
24 18
```

출력
```
6  
72
```