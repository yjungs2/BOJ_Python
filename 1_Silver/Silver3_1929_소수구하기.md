- 230111
## 백준 > Silver3 > 1929번 : 소수 구하기
메모리 30616kb 시간 3236ms  
https://www.acmicpc.net/problem/1929  

코드
```python
m, n = map(int, input().split())
def is_prime(x): # 소수 판별 함수
  for i in range(2, int(x**0.5)+1):
    if x%i == 0:
      return False
  return True
for i in range(m, n+1): # m 이상 n 이하의 자연수가
  if i != 1 and is_prime(i) == True: # 1은 소수가 아니므로 조건 추가 & 소수라면
    print(i) # 출력
```

입력
```
3 16
```

출력
```
3
5
7
11
13
```