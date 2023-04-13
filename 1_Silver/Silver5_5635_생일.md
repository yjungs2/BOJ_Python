- 221115
## 백준 > Silver5 > 5635번 : 생일
메모리 30840kb 시간 72ms  
https://www.acmicpc.net/problem/5635  

코드
```python
n = int(input())
info = []
name = ""
birth = ""
minb = 19901231 # 나이가 적은 사람의 생일
maxb = 20101231 # 나이가 많은 사람의 생일
minn = "" # 나이가 적은 사람의 이름
maxn = "" # 나이가 많은 사람의 이름
for _ in range(n):
    info = list(input().split(" "))
    name = info[0] # 학생의 이름 정보
    if len(info[1])==1:
        info[1] = "0"+info[1]
    if len(info[2])==1:
        info[2] = "0"+info[2]
    birth = int(info[3]+info[2]+info[1]) # 학생의 생년월일 정보
    if birth > minb: # 나이가 적다면
        minb = birth # 생일 업데이트
        minn = name # 이름 업데이트
    if birth < maxb: # 나이가 많다면
        maxb = birth # 생일 업데이트
        maxn = name # 이름 업데이트
print(minn)
print(maxn)
```

입력
```
5  
Mickey 1 10 1991  
Alice 30 12 1990  
Tom 15 8 1993  
Jerry 18 9 1990  
Garfield 20 9 1990
```

출력
```
Tom  
Jerry
```