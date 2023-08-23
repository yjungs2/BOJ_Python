- 220604
##  백준 > Bronze2 > 2675번 : 문자열 반복
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/2675  

코드
```python
t = int(input())
for i in range(t):
    answer = ''
    r, p = input().split(' ')
    for i in p:
        answer += i*int(r)
    print(answer)
```

입력
```
2
3 ABC
5 /HTP
```

출력
```
AAABBBCCC
/////HHHHHTTTTTPPPPP
```