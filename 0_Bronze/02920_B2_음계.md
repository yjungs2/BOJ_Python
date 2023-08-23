- 220605
##  백준 > Bronze2 > 2920번 : 음계
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/2920  

코드
```python
a = input()
if a == '1 2 3 4 5 6 7 8':
    print('ascending')
elif a == '8 7 6 5 4 3 2 1':
    print('descending')
else:
    print('mixed')
```

입력
```
1 2 3 4 5 6 7 8

8 7 6 5 4 3 2 1

8 1 7 2 6 3 5 4
```

출력
```
ascending

descending

mixed
```