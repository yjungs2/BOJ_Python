- 220616
##  백준 > Bronze1 > 1357번 : 뒤집힌 덧셈
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/1357  

코드
```python
x, y = map(int, input().split(' ')) # 입력받은 두 양의 정수 x, y
xlist = list(str(x)) # 정수 -> 문자열 -> 리스트
ylist = list(str(y))
xlist.reverse() # 뒤집기
ylist.reverse()
revx = int(''.join(xlist)) # 리스트 -> 문자열 -> 정수
revy = int(''.join(ylist))
sumxy = revx + revy # Rev(x) + Rev(y)
# Rev(Rev(x) + Rev(y))
if len(str(sumxy)) == 1:
    print(sumxy)
elif len(str(sumxy)) == 2:
    print((sumxy%10)*10 + sumxy//10)
elif len(str(sumxy)) == 3:
    print((sumxy%10)*100 + ((sumxy%100)//10)*10 + (sumxy//100))
elif len(str(sumxy)) == 4:
    print((sumxy%10)*1000 + ((sumxy%100)//10)*100 + ((sumxy%1000)//100)*10 + (sumxy//1000))
```

입력
```
456 789
```

출력
```
1461
```