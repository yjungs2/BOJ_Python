- 220731
## 백준 > Silver4 > 1026번 : 보물
메모리 30840kb 시간72ms  
https://www.acmicpc.net/problem/1026  

코드
```python
n = int(input()) # 길이 n
a = list(map(int, input().split())) # 정수 배열 a
b = list(map(int, input().split())) # 정수 배열 b
a.sort() # 배열 a 오름차순 정렬
b.sort() # 배열 b 오름차순 정렬
for i in a: # 배열 a에
    if i == 0: # 0이 있다면
        a.remove(0) # 배열에서 0 제거
a.reverse() # 배열 뒤집기 -> 내림차순 정렬
mins = 0
for j in range(len(a)):
    mins += a[j]*b[j]
print(mins) # s의 최솟값 출력
```

입력
```
9
5 15 100 31 39 0 0 3 26
11 12 13 2 3 4 5 9 1
```

출력
```
528
```