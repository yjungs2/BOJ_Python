- 220618
##  백준 > Bronze1 > 1259번 : 팰린드롬수
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/1259  

코드
```python
while True:
    a = int(input())
    if a == 0:
        break
    else:
        alist = list(str(a))
        arev = alist[::-1] # 뒤집은 alist를 변수 arev에 저장
        if alist == arev: # 팰린드롬수면
            print("yes")
        else: # 팰린드롬수가 아니면
            print("no")
```

```
프로그래머스에서 비슷한 문제를 풀었던 기억이 남아있는 문제.
* 리스트[::-1]은 기존 리스트 뒤집기!!
```

입력
```
121
1231
12421
0
```

출력
```
yes
no
yes
```