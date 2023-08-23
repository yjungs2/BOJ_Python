- 220619
##  백준 > Bronze1 > 1292번 : 쉽게 푸는 문제
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/1292  

코드
```python
a, b = map(int, input().split(' '))
i = 1
nlist = [1]
ncul = [1]
while True:
    i += 1
    nlist.append(i) # [1, 2, 3, 4, 5, ...]
    ncul.append(i + ncul[i-2]) # [1, 3, 6, 10, 15, ...]
    if b <= (i + ncul[i-2]):
        break
answer = 0
for j in range(a, b+1):
    if j == 1:
        answer += 1
    for i in range(len(ncul)):
        if j > ncul[i] and j <= ncul[i+1]:
            answer += nlist[i+1] # a번째 숫자부터 b번째 숫자까지의 합
print(answer)
```

시행착오
```
처음에 a = 1이라 1부터 시작하는 경우를 고려하지 않아서 틀렸다.
-> j == 1인 경우를 if문으로 추가해주었다.
```

입력
```
3 7
```

출력
```
15
```

테스트 과정
```
1 45
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 3, 6, 10, 15, 21, 28, 36, 45]
1
2
2
3
3
3
4
4
4
4
5
5
5
5
5
6
6
6
6
6
6
7
7
7
7
7
7
7
8
8
8
8
8
8
8
8
9
9
9
9
9
9
9
9
9
285
```