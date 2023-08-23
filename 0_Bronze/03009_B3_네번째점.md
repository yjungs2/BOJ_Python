- 220609
##  백준 > Bronze3 > 3009번 : 네 번째 점
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/3009  

코드
```python
xlist = []
ylist = []
for i in range(3):
    x, y = map(int, input().split(' '))
    xlist.append(x) # 세 점의 x값 리스트
    ylist.append(y) # 세 점의 y값 리스트
findx = xlist[0]
xlist.remove(findx)
findy = ylist[0]
ylist.remove(findy)
if findx in xlist: # xlist에 findx와 같은 값이 존재하면
    xlist.remove(findx)
    findx = xlist[0] # 기존 findx와 다른 값으로 findx를 갱신한다
if findy in ylist: # ylist에 findy와 같은 값이 존재하면
    ylist.remove(findy)
    findy = ylist[0] # 기존 findy와 다른 값으로 findy를 갱신한다
print(f"{findx} {findy}")
```

```
xlist와 ylist에 세 점의 x값들, y값들을 각각 담아서
각 리스트에서 하나만 있는 수를 찾으면 되는데 코드로 짜려니 생각보다 쉽지 않았던 것 같다.
```

입력
```
5 5
5 7
7 5
```

출력
```
7 7
```