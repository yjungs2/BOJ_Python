- 220614
##  백준 > Bronze1 > 4344번 : 평균은 넘겠지
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/4344  

코드
```python
c = int(input())
for i in range(c):
    nlist = list(map(int, input().split(' ')))
    n = nlist[0] # 학생의 수
    nsum = 0
    nave = 0
    for j in range(1, n+1):
        nsum += nlist[j] # 점수의 합
    nave = nsum/n # 점수의 평균
    upave = 0
    for k in range(1, n+1):
        if nlist[k] > nave:
            upave += 1 # 평균을 넘는 사람 수
    # 평균 넘는 학생들의 비율 반올림(소수점 셋째 자리까지) 출력
    print(f"{format((upave/n)*100, '.3f')}%")
```

```
round((upave/n)*100, 3)으로 출력하면 40.0이 나오므로
소수점 끝자리가 0인 수를 출력하려면 format((upave/n)*100, '.3f')로 출력해준다.
여기서'.3f'는 소수점 셋째자리까지 출력한다는 의미이다.
```

입력
```
5
5 50 50 70 80 100
7 100 95 90 80 70 60 50
3 70 90 80
3 70 90 81
9 100 99 98 97 96 95 94 93 91
```

출력
```
40.000%
57.143%
33.333%
66.667%
55.556%
```