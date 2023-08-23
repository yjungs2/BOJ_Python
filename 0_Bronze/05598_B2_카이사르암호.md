- 230101
## 백준 > Bronze2 > 5598번 : 카이사르 암호
메모리 30616kb 시간 32ms  
https://www.acmicpc.net/problem/5598  

```
카이사르(Gaius Julius Caesar)
변환전    A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
변환후    D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
```

코드
```python
caesar = list(input()) # 입력받은 카이사르 단어
word = []
for i in caesar:
  if ord(i) >= 68: # 'D' ~ 'Z'라면
    newi = chr(ord(i)-3)
  else: # 'A' ~ 'C'라면
    newi = chr(ord(i)+23)
  word.append(newi) # 원래 단어로 고친 걸 넣기
print("".join(word))
```

입력
```
MRL

FURDWLD
```

출력
```
JOI

CROATIA
```