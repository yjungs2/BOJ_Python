- 221123
## 백준 > Bronze2 > 2231번 : 분해합
메모리 30840kb 시간 2572ms  
https://www.acmicpc.net/problem/2231  

코드
```python
n = int(input()) # 자연수 n
ans = 0 # 생성자 담을 변수. 생성자가 없으면 0 출력
for i in range(1, n): # n보다 작은 수 중에서 
    eachi = 0
    for j in range(0, len(str(i))):
        eachi += (i//(10**j))%(10) # 각 자리 수의 합 계산
    if (i+eachi) == n: # i의 분해합(i와 i를 이루는 각 자리수의 합)이 n과 같으면
        ans = i # 생성자는 i
        break
print(ans) # n의 가장 작은 생성자 출력
```

입력
```
216
```

출력
```
198
```