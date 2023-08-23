- 221116
## 백준 > Silver5 > 1316번 : 그룹 단어 체커
메모리 30840kb 시간 80ms  
https://www.acmicpc.net/problem/1316  

코드
```python
n = int(input()) # 단어의 개수
ans = n
for _ in range(n):
    word = input() # 입력받는 단어
    alpha = [word[0]] # 단어에 들어가는 알파벳 리스트
    for i in range(1, len(word)):
        if word[i] != word[i-1] and word[i] in alpha: # 앞과 다르면서 이미 리스트에 존재하면
            ans -= 1 # 그룹 단어가 아니다
            break # for문 중단
        else:
            if word[i] != word[i-1] and word[i] not in alpha: # 앞과 다르면서 리스트에 존재하지 않으면
                alpha.append(word[i]) # 리스트에 해당 알파벳 추가
print(ans) # 그룹 단어 개수 출력
```

입력
```
15  
happy  
new  
year  
aba  
abab  
abcabc  
a  
ab  
aa  
aca  
ba  
bb  
yzyzy  
zyzyz  
z  
```

출력
```
9
```