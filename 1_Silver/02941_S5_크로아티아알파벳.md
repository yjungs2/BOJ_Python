- 220315
##  백준 > Silver5 > 2941번 : 크로아티아 알파벳

코드 (런타임 에러)
```python
word = input()
word_list = list(word)
count = len(word_list)
for i in range(len(word_list)):
    if word_list[i]=="c" and (word_list[i+1]=="=" or word_list[i+1]=="-"):
        count -= 1
    if word_list[i]=="d" and word_list[i+1]=="z" and word_list[i+2]=="=":
        count -= 1 # 아래 "z="에서 한번 더 (count -1) 이 되므로 2가 아니라 1만 빼준다.
    if word_list[i]=="d" and word_list[i+1]=="-":
        count -= 1
    if word_list[i]=="l" and word_list[i+1]=="j":
        count -= 1
    if word_list[i]=="n" and word_list[i+1]=="j":
        count -= 1
    if word_list[i]=="=" and (word_list[i-1]=="s" or word_list[i-1]=="z"):
        count -= 1
    else:
        count = count
print(count)
```

코드
```python
word = input()
croatia = ['c=', 'c-', 'dz=', 'd-', 'lj', 'nj', 's=', 'z='] # 크로아티아 알파벳 배열

for i in croatia:
    if i in word:
        word = word.replace(i, "a") # word에 croatia 알파벳이 있으면 한 글자로 세기 위해 "a"로 대체

print(len(word))
```

입력
```
ljes=njak
ddz=z=
nljj
c=c=
dz=ak
```

출력
```
6
3
3
2
3
```