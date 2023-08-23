- 220315
##  백준 > Bronze2 > 2789번 : 유학 금지

코드
```python
word = input()

for i in "CAMBRIDGE":
    word = word.replace(i, "")
    
print(word)
```

입력
```
LOVA
KARIJERA
```

출력
```
LOV
KJ
```