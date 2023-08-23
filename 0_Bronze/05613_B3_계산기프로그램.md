- 230202
##  백준 > Bronze3 > 5613번 : 계산기 프로그램
메모리 31256kb 시간 48ms  
https://www.acmicpc.net/problem/5613  

코드
```python
num = int(input()) # 처음 주어진 수
while(True): # 입력 순서대로 계산
  ope = input()
  if ope == "=": # =가 주어지면
    break # while문 중단
  else: # 사칙연산이라면
    num2 = int(input())
    if ope == "+":
      num += num2
    elif ope == "-":
      num -= num2
    elif ope == "*":
      num *= num2
    else:
      num = int(num/num2) # 나눗셈에서 소수점 버림
print(num)
```

입력
```
10
-
21
*
5
=

100
/
3
*
3
=
```

출력
```
-55

99
```