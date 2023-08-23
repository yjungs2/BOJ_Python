- 220720
## 백준 > Bronze1 > 1032번 : 명령 프롬프트
메모리 30840kb 시간72ms  
https://www.acmicpc.net/problem/1032  

코드
```python
n = int(input()) # 파일 이름의 개수
files = [[] for i in range(n+1)] # 배열 files 생성
for i in range(n):
    file = input()
    files[i] = list(file)
    if i == 0:
        files[n] = list(file) # n행에는 0행과 같은 데이터 넣어주기
flen = len(files[0]) # 파일 이름의 길이
for i in range(1, n):
  for j in range(flen):
    if files[n][j] == '?': # 이미 '?'라면
        pass # 넘어가기
    elif files[i][j] != files[i-1][j]: # 같은 위치의 문자가 다르다면
        files[n][j] = '?' # '?' 로 바꾸기
    else: # 같은 위치의 문자가 같은데
      if files[n][j] != '?': # '?'가 아니라면
        files[n][j] = files[i][j] # 기존 문자가 자리함
print("".join(files[n])) # 패턴 출력
```

입력
```
3
config.sys
config.inf
configures
```

출력
```
config????
```