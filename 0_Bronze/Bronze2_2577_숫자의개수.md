- 220603
##  백준 > Bronze2 > 2577번 : 숫자의 개수
메모리 30840kb 시간 72ms  
https://www.acmicpc.net/problem/2577  

코드
```python
a = int(input()) # 입력값은 str이므로 int형을 변수에 담음
b = int(input())
c = int(input())
mulnum = a*b*c # 세 자연수 a, b, c의 곱
numlist = list(str(mulnum)) # 곱 연산 결과를 리스트에 담음
anslist = [0] * 10 # 개수를 셀 크기 10인 리스트 생성
for i in range(0, 10):
    for n in numlist:
        if str(i) == n:
            anslist[i] += 1 # 숫자가 사용되었으면 해당 수가 인덱스인 anslist 원소 수 1 증가
for k in anslist:
    print(k)
```

입력
```
150
266
427
```

출력
```
3
1
0
2
0
0
0
2
0
0
```