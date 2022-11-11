- 220606
##  백준 > Bronze2 > 2908번 : 상수
메모리 30840kb 시간 72ms  
https://www.acmicpc.net/problem/2908  

코드
```python
a, b = map(int, input().split(' '))
lia = list(str(a)) # 정수 a -> 문자열 -> 리스트에 담기
lia.reverse() # 리스트 뒤집기
rea = int(''.join(lia)) # 리스트 -> 문자열 -> 정수 (a를 거꾸로 읽은 수)
lib = list(str(b)) # 정수 b -> 문자열 -> 리스트에 담기
lib.reverse() # 리스트 뒤집기
reb = int(''.join(lib)) # 리스트 -> 문자열 -> 정수 (b를 거꾸로 읽은 수)
print(max(rea, reb))
```

입력
```
734 893
```

출력
```
437
```