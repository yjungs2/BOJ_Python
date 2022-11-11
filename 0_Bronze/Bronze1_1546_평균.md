- 220607
##  백준 > Bronze1 > 1546번 : 평균
메모리 30840kb 시간 72ms  
https://www.acmicpc.net/problem/1546  

코드
```python
n = int(input()) # 과목의 개수
score = list(map(int, input().split(' '))) # 시험점수(정수)를 리스트에 담음
maxsc = max(score) # 최고점
sumsc = 0 # 점수의 합
for i in score:
    sumsc += i
print(sumsc/maxsc*100/n)
```

입력
```
4
10 20 0 100

9
10 20 30 40 50 60 70 80 90
```

출력
```
32.5

55.55555555555556
```