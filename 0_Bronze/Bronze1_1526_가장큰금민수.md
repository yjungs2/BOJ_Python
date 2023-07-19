- 221211
## 백준 > Bronze1 > 1526번 : 가장 큰 금민수
(1) 메모리 30616kb 시간 412ms  
(2) 메모리 31256kb 시간 288ms  
https://www.acmicpc.net/problem/1526  

과정
```
1자리 수 2개 (4, 7)  
2자리 수 4개 (44, 47, 74, 77)  
3자리 수 8개 (444, 447, 474, 477, 744, 747, 774, 777)  
...
이런 식으로 n의 자릿수에 따라 경우를 나누는 방식을 처음에 고려했으나  
이 방법을 쓰려면 크게 6가지로 나누고 또 세분화해야해서
분류에 적힌 **브루트포스 알고리즘**으로 풀었다.
```

코드 (1)
```python
n = int(input()) # 입력값 정수 n
npart = []
ans = 0
for i in range(n, 3, -1): # n부터 4까지 줄이면서
  npart = list(str(i)) # 정수 n을 각 자리수 문자를 리스트에 담음
  cnt = 0
  for j in npart: # 각 자리 수가
    if j in ['4', '7']: # 4 또는 7이라면
      cnt += 1 # cnt 증가
  if cnt == len(str(i)): # 4 또는 7의 개수가 수의 길이와 같다면
    ans = i # 4와 7로만 이루어진 금민수이므로 정답
    break
print(ans)
```

코드 (2)
```python
n = int(input())
ans = 0
for i in range(n, 3, -1):
  if str(i).count('4') + str(i).count('7') == len(str(i)): # 숫자 i를 이루는 모든 수가 4나 7이라면
    ans = i
    break
print(ans)
```

입력
```
100

75

5

474747
```

출력
```
77

74

4

474747
```