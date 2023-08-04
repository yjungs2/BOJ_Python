- 230205
##  백준 > Bronze1 > 1296번 : 팀 이름 정하기
메모리 31256kb 시간 44ms  
https://www.acmicpc.net/problem/1296  

코드
```python
name = list(input()) # 연두의 영어이름
n = int(input()) # 팀 이름 후보 개수 n개
subname = []
pro = -1
ans = ""
for i in range(n):
  subname = list(input()) # 팀 이름 후보
  l = name.count("L") + subname.count("L") # 연두 이름과 팀 이름에 등장하는 L의 개수
  o = name.count("O") + subname.count("O") # O의 개수
  v = name.count("V") + subname.count("V") # V의 개수
  e = name.count("E") + subname.count("E") # E의 개수
  ipro = ((l+o)*(l+v)*(l+e)*(o+v)*(o+e)*(v+e)) % 100 # 팀 이름의 우승 확률
  if ipro > pro: # 기존의 확률보다 크면
    pro = ipro # 최고 확률 변경
    ans = "".join(subname) # 이름 변경
  elif ipro == pro: # 기존의 확률과 같다면
    ans = min(ans, "".join(subname)) # 사전 순 앞서는 이름 변경
print(ans) # 우승할 확률이 가장 높은 팀 이름 출력
```

입력
```
VELYLEOCEVE
5
YVXHOVE
LCOKO
OGWSJVEVEDLE
WGFVSJEL
VLOLUVCBLLQVESWHEEKC
```

출력
```
VLOLUVCBLLQVESWHEEKC
```