- 220628
##  백준 > Silver5 > 1427번 : 소트인사이드
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/1427  

코드
```python
n = int(input())
nlist = list(str(n))
nlist.sort(reverse = True) # 내림차순 정렬
print("".join(nlist))
```
```python
nlist = list(input())
nlist.sort(reverse = True) # 내림차순 정렬
print("".join(nlist))
```

입력
```
500613009
```

출력
```
965310000
```