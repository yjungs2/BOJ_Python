- 221111
## 백준 > Silver4 > 1065번 : 한수
코드(1) 메모리 30840kb 시간 72ms  
코드(2) 메모리 31256kb 시간 40ms  
https://www.acmicpc.net/problem/1065  

```
조건 : 첫째 줄에 1,000보다 작거나 같은 자연수 N  
1자리 숫자 -> 모두 한수  
2자리 숫자 -> 모두 한수  
3자리 숫자인 경우만 등차 계산해서 한수인지 아닌지 판단하기
```

코드 (1)
```python
n = input() # 문자 그대로 n
intn = int(n) # 정수 n
ans = 0
if len(n)<=2: # n이 2자리수 이하라면
    ans = intn # 답은 정수 n
else:
    ans = 99
    ansli = [] # 100 이상 한수 리스트
    for i in range(100, intn+1):
        seq = [] # 등차 담을 리스트
        for j in range(len(str(i))-1):
            seq.append(int(str(i)[j+1]) - int(str(i)[j])) # 문자를 정수로 바꿔서 등차 계산
        if len(set(seq)) == 1: # 등차가 하나라면 (일정하다면)
            ansli.append(i) # 정수 i는 한수
    ans += len(ansli)
print(ans)
```

코드 (2)
```python
n = input() # 문자 그대로 n
intn = int(n) # 정수 n
ans = 0
if len(n)<=2: # n이 2자리수 이하라면
    ans = intn # 답은 정수 n
else:
    ans = 99
    for i in range(100, intn+1):
        if (int(str(i)[2]) - int(str(i)[1])) == (int(str(i)[1]) - int(str(i)[0])): # 등차가 일정하다면
            ans += 1
print(ans)
```

입력
```
1

110

210

500

1000
```

출력
```
1

99

105

119

144
```