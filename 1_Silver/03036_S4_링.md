- 230103
## 백준 > Silver4 > 3036번 : 링
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/3036  

코드
```python
def gcd(a,b): # 최대공약수 정의
  if a%b == 0:
    return b
  else:
    return gcd(b, a%b)
n = int(input()) # 링의 개수
nums = list(map(int, input().split())) # 링의 반지름 리스트
for i in range(1, n): # (링의 개수 - 1)만큼
  ring = [nums[0], nums[i]] # 첫번째 링과 각각의 링에 대해서
  a = max(ring)
  b = min(ring)
  abgcd = gcd(a,b) # 최대공약수를 찾아서
  print(f"{nums[0]//abgcd}/{nums[i]//abgcd}") # 기약분수 형태로 출력
```

입력
```
3
8 4 2

4
12 3 8 4

4
300 1 1 300
```

출력
```
2/1
4/1

4/1
3/2
3/1

300/1
300/1
1/1
```