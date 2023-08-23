- 221206
## 백준 > Bronze2 > 1075번 : 나누기
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/1075  

코드
```python
n = int(input()) # 정수 n
f = int(input()) # 정수 f
newn = (n//100)*100 # 정수 n을 뒤 두자리 수가 00인 수로 변경
ans = 0
for i in range(0, 100): # 00부터 99까지 더한 newn이
  if (newn + i) % f == 0: # f로 나누어 떨어지면
    ans = i
    break # 중단
  else:
    continue
if ans//10 == 0: # 정답이 한 자리 수이면
  ans = str(0)+str(ans) # 앞에 0을 추가해서 두 자리로 만듦
print(ans)
```

입력
```
1000  
3  

23442  
75  

428392  
17  

32442  
99
```

출력
```
02  

00  

15  

72
```