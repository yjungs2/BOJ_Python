- 220606
##  백준 > Bronze2 > 3052번 : 나머지
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/3052  

코드
```python
num = [] # 입력받는 숫자 담을 리스트
res = [] # 나머지 결과 담을 리스트
ans = [] # 서로 다른 값 담을 리스트
for i in range(10):
    num.append(int(input()))
for j in num:
    res.append(j%42)
for k in res:
    if k not in ans:
        ans.append(k)
print(len(ans))
```

입력
```
39
40
41
42
43
44
82
83
84
85
```

출력
```
6
```