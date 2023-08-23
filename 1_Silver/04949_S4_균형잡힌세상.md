- 220724
## 백준 > Silver4 > 4949번 : 균형잡힌 세상
메모리 30840kb 시간396ms  
https://www.acmicpc.net/problem/4949  

코드
```python
while True:
    sen = input() # 입력 문자열로 받기
    if sen == '.': # 점 하나가 들어오면
        break # 입력이 종료됨
    else:
        plist = []
        for i in range(len(sen)): # 문자열 안에서
            if sen[i] in ['(', ')', '[', ']']: # 괄호가 있다면
                plist.append(sen[i]) # 괄호를 plist 리스트에 담기
        pstr = "".join(plist) # 리스트를 문자열로 변경
        for j in range(len(pstr)//2): # 문자열 길이 절반만큼 for문 돌면서
            if '()' in pstr: # 소괄호 짝이 있다면
                pstr  = pstr.replace('()', '') # 소괄호 짝 없애기
            if '[]' in pstr: # 대괄호 짝이 있다면
                pstr = pstr.replace('[]', '') # 대괄호 짝 없애기
        if len(pstr) == 0: # 길이가 0이라면 = 괄호가 모두 짝을 이루면
            print('yes')
        else:
            print('no')
```

```
균형잡힌 세상(4949번) 문제는 괄호(9012번) 문제랑 같은 방법으로 풀었다.
영어와 괄호가 섞여있는 문자열에서 괄호만 뽑은 뒤에,
문자열 길이 절반만큼 for문 돌면서 짝 있는 괄호 (), []를 찾아냈다.
최종적으로 짝 있는 괄호가 모두 사라지고
문자열의 길이가 0이 되면, 문자열이 균형을 이루고 있으므로 'yes'를 출력하고
문자열의 길이가 0이 아니라면, 문자열이 균형을 이루고 있지 않으므로 'no'를 출력한다.
```

입력
```
So when I die (the [first] I will see in (heaven) is a score list).
[ first in ] ( first out ).
Half Moon tonight (At least it is better than no Moon at all].
A rope may form )( a trail in a maze.
Help( I[m being held prisoner in a fortune cookie factory)].
([ (([( [ ] ) ( ) (( ))] )) ]).
 .
.
```

출력
```
yes
yes
no
no
no
yes
yes
```