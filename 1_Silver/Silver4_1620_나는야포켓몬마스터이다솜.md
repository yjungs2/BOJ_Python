- 230127
## 백준 > Silver4 > 1620번 : 나는야 포켓몬 마스터 이다솜
(2) 메모리 50688kb 시간 236ms  
(3) 메모리 55064kb 시간 248ms  
https://www.acmicpc.net/problem/1620  

```
여기서 숫자는 정수만 사용하므로 **isdigit()** 사용  

(1) 딕셔너리 1개 사용 -> 이름 검색 이중 for문 돌기 -> 시간초과  
(2) 딕셔너리 2개 사용  
mons = dict() # 번호 검색 딕셔너리  
nums = dict() # 이름 검색 딕셔너리  
(3) 딕셔너리 1개 사용  
mons = dict() # 번호 검색 & 이름 검색 동시에
```

코드 (1)
```python
# 시간초과
n, m = map(int, input().split())
mons = dict()
for i in range(1, n+1):
  mons[i] = input()
for j in range(m):
  what = input()
  if what.isdigit() == True:
    print(mons[int(what)])
  else:
    for i in range(1, n+1):
      if mons[i] == what:
        print(i)
```

코드 (2)
```python
import sys
input = sys.stdin.readline

n, m = map(int, input().split())
mons = dict() # 번호 검색 딕셔너리
nums = dict() # 시간초과 해결용 이름 검색 딕셔너리 (다른 분 코드 참고)
for i in range(1, n+1):
  mon = input().rstrip()
  mons[i] = mon # key(번호):value(포켓몬) 저장
  nums[mon] = i # key(포켓몬):value(번호) 저장
for j in range(m):
  what = input().rstrip()
  if what.isdigit() == True: # 입력이 숫자라면
    print(mons[int(what)])
  else: # 입력이 문자라면
    print(nums[what])
```

코드 (3)
```python
import sys
input = sys.stdin.readline

n, m = map(int, input().split())
mons = dict() # 번호 검색 & 이름 검색 동시에 가능한 딕셔너리
for i in range(1, n+1):
  name = input().rstrip() # 런타임에러(KeyError) 해결 위해 rstrip() 사용
  mons[i] = name # key(번호):value(포켓몬) 저장
  mons[name] = i # key(포켓몬):value(번호) 저장
for j in range(m):
  what = input().rstrip() # 런타임에러(KeyError) 해결 위해 rstrip() 사용
  if what.isdigit() == True: # 입력이 숫자라면
    print(mons[int(what)])
  else: # 입력이 문자라면
    print(mons[what])
```

입력
```
26 5
Bulbasaur
Ivysaur
Venusaur
Charmander
Charmeleon
Charizard
Squirtle
Wartortle
Blastoise
Caterpie
Metapod
Butterfree
Weedle
Kakuna
Beedrill
Pidgey
Pidgeotto
Pidgeot
Rattata
Raticate
Spearow
Fearow
Ekans
Arbok
Pikachu
Raichu
25
Raichu
3
Pidgey
Kakuna
```

출력
```
Pikachu
26
Venusaur
16
14
```