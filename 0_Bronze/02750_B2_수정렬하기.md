- 220611
##  백준 > Bronze2 > 2750번 : 수 정렬하기
메모리 30840kb 시간 104ms  
https://www.acmicpc.net/problem/2750  

코드
```python
n = int(input())
nlist = []
for i in range(n):
    a = int(input())
    nlist.append(a)
nlist.sort() # 오름차순 정렬
for j in nlist:
    print(j)
```

입력
```
5
5
2
3
4
1
```

출력
```
1
2
3
4
5
```