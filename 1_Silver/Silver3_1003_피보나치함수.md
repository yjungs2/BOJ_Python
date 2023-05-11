- 221204
## 백준 > Silver3 > 1003번 : 피보나치 함수
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/1003  

코드
```python
t = int(input()) # 테스트 케이스 개수 t
nums = []
zero = [1, 0] # 0이 출력되는 횟수
one = [0, 1] # 1이 출력되는 횟수
for _ in range(t):
  nums.append(int(input())) # 구할 피보나치 수
for i in range(2, max(nums)+1):
  zero.append(zero[i-2] + zero[i-1]) # 피보나치 수에서 0이 출력되는 횟수 계산
  one.append(one[i-2] + one[i-1]) # 피보나치 수에서 1이 출력되는 횟수 계산
for j in nums: # fibonacci(j)를 호출했을 때
  print(zero[j], one[j]) # 0과 1이 출력되는 횟수 출력
```

입력
```
5  
0  
1  
3  
6  
22
```

출력
```
1 0  
0 1  
1 2  
5 8  
10946 17711
```