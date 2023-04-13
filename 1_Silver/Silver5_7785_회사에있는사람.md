- 221119
## 백준 > Silver5 > 7785번 : 회사에 있는 사람
메모리 50588kb 시간 240ms  
https://www.acmicpc.net/problem/7785  

과정
```
(1) 시간 초과 해결 위해 input을 sys.stdin.readline으로 수정  
(2) 시간 초과 해결 위해 list에서 append, remove를 dict로 시도  
(3) 틀렸습니다. -> 뭐 틀렸지..?  
  input().split(" ") 은 가능한데  
  sys.stdin.readline().split(" ") 에서 오류가 나고  
  sys.stdin.readline().split()에선 오류가 나지 않는다.
```

코드
```python
import sys
input = sys.stdin.readline

n = int(input()) # 출입 기록 수 n
member = dict() # 출입 기록 dict
for i in range(n):
    name, log = input().split()
    if log == "enter": # 출입 기록이 enter면
        member[name] = 1 # 해당 이름의 값은 1
    elif log == "leave": # 출입 기록이 leave면
        member[name] = 0 # 해당 이름의 값은 0
member = sorted(member.items(), key=lambda x : x[0], reverse=True) # 이름의 역순으로 정렬
for j in member:
    if j[1] == 1: # 값이 1이면 (현재 회사에 있다면)
        print(j[0]) # 출력하기
```

입력
```
4
Baha enter
Askar enter
Baha leave
Artem enter
```

출력
```
Askar
Artem
```