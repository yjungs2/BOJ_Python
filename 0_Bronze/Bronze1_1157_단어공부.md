- 220622
##  백준 > Bronze1 > 1157번 : 단어 공부
메모리 32796kb 시간 248ms  
https://www.acmicpc.net/problem/1157  

코드
```python
word = input().upper()
asc = [0] * 26
# ord('A') = 65 ~ ord('Z') = 90
for i in word:
    asc[ord(i) - 65] += 1 # 알파벳의 아스키코드 배열 인덱스에 수 세기
maxal = []
for j in range(0, 26):
    if asc[j] == max(asc): # asc 배열의 수가 asc의 최댓값과 같다면
        maxal.append(chr(j+65)) # 아스키코드에 해당하는 문자를 배열에 추가
if len(maxal) == 1:
    print(maxal[0]) # 가장 많이 사용된 알파벳을 대문자로 출력
else: # 가장 많이 사용된 알파벳이 여러 개라면
    print('?') # ? 출력
```

입력
```
Mississipi

zZa

z

baaa
```

출력
```
?

Z

Z

A
```