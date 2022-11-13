- 220621
##  백준 > Bronze2 > 5622번 : 다이얼
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/5622  

코드
```python
word = input()
time = 0
for i in word:
    if ord(i) >= 65 and ord(i) <= 67: # A, B, C
        time += 3
    elif ord(i) >= 68 and ord(i) <= 70: # D, E, F
        time += 4
    elif ord(i) >= 71 and ord(i) <= 73: # G, H, I
        time += 5
    elif ord(i) >= 74 and ord(i) <= 76: # J, K, L
        time += 6
    elif ord(i) >= 77 and ord(i) <= 79: # M, N, O
        time += 7
    elif ord(i) >= 80 and ord(i) <= 83: # P, Q, R, S 
        time += 8
    elif ord(i) >= 84 and ord(i) <= 86: # T, U, V
        time += 9
    elif ord(i) >= 87 and ord(i) <= 90: # W, X, Y, Z
        time += 10
print(time)
```

시행착오
```
처음엔 아스키 코드 값을 이용하지 않고,
if i in ['A', 'B', 'C'] 부터 elif i in ['W', 'X', 'Y', 'Z']로 코드를 짰는데
이 방식에서 'I(대문자 i)'를 인식하지 못한다는 것을 알았다.
찾아보니 대문자 i(I)와 대문자 o(O)는 인식하지 못한다는 것 같은데 이에 대한 정보가 많지 않았다.
결국 이런 오류가 없을 아스키코드로 if문을 짜게 되었다.
```

입력
```
WA

UNUCIC
```

출력
```
13

36
```