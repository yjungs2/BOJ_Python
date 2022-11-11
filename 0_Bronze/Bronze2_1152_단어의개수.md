##  백준 > Bronze2 > 1152번 단어의 개수

```python
sen = input()
answer = []
wlist = list(sen.split(" "))
for i in wlist:
    if i != "":
        answer.append(i)
print(answer)
print(len(answer))
```

입력
```
The first character is a blank
```

결과
```
['The', 'first', 'character', 'is', 'a', 'blank']
6
```