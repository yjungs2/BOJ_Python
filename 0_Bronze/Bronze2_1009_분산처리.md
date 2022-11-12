- 220612
##  백준 > Bronze2 > 1009번 : 분산처리
메모리 30840kb 시간 104ms  
https://www.acmicpc.net/problem/1009  

아이디어
```
a^b의 형태로 주어지면 1의 자리수가 반복된다는 점을 활용했다.
1 : 1
2 : 2 - 4 - 8 - 6
3 : 3 - 9 - 7 - 1
4 : 4 - 6
5 : 5
6 : 6
7 : 7 - 9 - 3 - 1
8 : 8 - 4 - 2 - 6
9 : 9 - 1
10 : 10
+ 이 방법을 안 쓰면 시간초과가 뜬다고 한다.
```

코드
```python
t = int(input()) # 테스트 케이스 개수
for i in range(t):
    a, b = map(int, input().split(' ')) # 총 데이터 개수 a^b
    if a%10 == 1 or a%10 == 5 or a%10 == 6:  # a의 1의 자리가 1, 5, 6이면 1, 5, 6 출력
        print(a%10)
    if a%10 == 0: # a의 1의 자리가 0이면 10 출력
        print(10)
    if a%10 == 4: # a의 1의 자리가 4이면 4, 6 반복 출력
        if b%2 == 1:
            print(4)
        elif b%2 == 0:
            print(6)
    if a%10 == 9: # a의 1의 자리가 9면 9, 1 반복 출력
        if b%2 == 1:
            print(9)
        elif b%2 == 0:
            print(1)
    if a%10 == 2: # a의 1의 자리가 2이면 2, 4, 8, 6 반복 출력
        if b%4 == 1:
            print(2)
        elif b%4 == 2:
            print(4)
        elif b%4 == 3:
            print(8)
        elif b%4 == 0:
            print(6)
    if a%10 == 3: # a의 1의 자리가 3이면 3, 9, 7, 1 반복 출력
        if b%4 == 1:
            print(3)
        elif b%4 == 2:
            print(9)
        elif b%4 == 3:
            print(7)
        elif b%4 == 0:
            print(1)
    if a%10 == 7: # a의 1의 자리가 7이면 7, 9, 3, 1 반복 출력
        if b%4 == 1:
            print(7)
        elif b%4 == 2:
            print(9)
        elif b%4 == 3:
            print(3)
        elif b%4 == 0:
            print(1)
    if a%10 == 8: # a의 1의 자리가 8이면 8, 4, 2, 6 반복 출력
        if b%4 == 1:
            print(8)
        elif b%4 == 2:
            print(4)
        elif b%4 == 3:
            print(2)
        elif b%4 == 0:
            print(6)
```

입력
```
5
1 6
3 7
6 2
7 100
9 635
```

출력
```
1
7
6
1
9
```