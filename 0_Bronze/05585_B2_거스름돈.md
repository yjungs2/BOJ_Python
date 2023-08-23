- 220608
##  백준 > Bronze2 > 5585번 : 거스름돈
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/5585  

```
380 -> 620 = 500 +100+10+10 -> 4
1 -> 999 = 500 + 100 * 4 + 50 + 10 * 4 + 5 + 1 * 4 -> 15
```

코드
```python
a = int(input()) # 물건 가격
money = 1000 - a # 잔돈 가격
answer = 0
list = [500, 100, 50, 10, 5, 1] # 잔돈 금액 리스트
for i in list:
    answer += money//i # 잔돈의 개수
    money -= i*(money//i)
print(answer)
```

입력
```
380

1
```

출력
```
4

15
```