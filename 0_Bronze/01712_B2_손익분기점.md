- 220608
##  백준 > Bronze2 > 1712번 : 손익분기점
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/1712  

코드
```python
a, b, c = map(int, input().split()) # 고정비용 a, 가변비용 b, 가격c
if b < c:
    t = a//(c-b) # 위치 조심!! 런타임 에러 (ZeroDivisionError)
    while True:
        t += 1
        if (a + b * t) < (c * t): # 최초로 이익이 발생하면
            break
    print(t) # 손익분기점 출력
elif b >= c: # 손익분기점이 존재하지 않으면
    print(-1) # -1 출력
```

시행착오
```
처음 짠 손익분기점 코드는 실행 시간이 너무 길어서 고민하다
t 초기값을 넣어서 실행 시간을 단축시켰다. (t = a//(c-b))
하지만 그 결과도 '런타임 에러 (ZeroDivisionError)'... (정답 비율이 낮은데는 이유가..?)
그래도 런타임 에러가 ZeroDivisionError라 코드 한줄 위치 바꾸는 걸로 해결했다. (if문 안에 넣기!)
```

입력
```
1000 70 170

3 2 1

2100000000 9 10
```

출력
```
11

-1

2100000001
```