- 221207
## 백준 > Silver4 > 1543번 : 문서 검색
메모리 30616kb 시간 40ms  
https://www.acmicpc.net/problem/1543  

코드
```python
docu = list(input()) # 검색할 문서
word = input() # 검색하는 단어
pos = [] # 단어의 등장 위치 저장할 리스트
ans = 0 # 중복되지 않고 등장하는 단어 개수
for i in range(0, len(docu)-len(word)+1): # 문서의 앞에서부터 차례대로 돌면서
  if "".join(docu[i:i+len(word)]) == word: # 단어길이만큼의 문서가 단어와 같으면
    docu[i:i+len(word)] = ["0"]*len(word) # 해당 문서를 숫자 문자로 변경하고
    pos.append(i) # 단어 등장 위치를 기록함
#print(pos)
print(len(pos)) # 위치의 개수 출력
```

과정
```
docu를 list가 아닌 str로 받으니  
**'str' object does not support item assignment** 오류로  
if 조건일 때 변경이 안 되어서 list로 입력을 받아 해결하였다.
```

입력
```
ababababa  
aba  

a a a a a  
a a  

ababababa  
ababa  

aaaaaaa  
aa
```

출력
```
2  

2  

1  

3
```