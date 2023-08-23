- 220627
##  백준 > Silver4 > 9012번 : 괄호
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/9012  

코드
```python
t = int(input()) # 테스트 케이스 t
for i in range(t):
    ps = input() # 입력 괄호 문자열 ps
    if len(ps) % 2 != 0: # ps 길이가 홀수이면
        print('NO') # VPS 아님
    else: # ps 길이가 짝수이면
        for n in range(len(ps)//2): # 길이 절반만큼 for문 돌면서
            ps = ps.replace('()', '') # '()'를 삭제
        if len(ps) == 0: # ps 길이가 0이면
            print('YES') # VPS
        else: # ps에 문자가 남아있으면
            print('NO') # VPS 아님
```

시행착오
```
처음에 함수 정의 def + while True 로 풀려다가 실패하고
결국 원래 풀던 방식 + for n in range(len(ps)//2)로 해결했다.
찾아보니 스택 문제라던데... 문자열로 풀었다..!
```

입력
```
6
(())())
(((()())()
(()())((()))
((()()(()))(((())))()
()()()()(()()())()
(()((())()(
```

출력
```
NO
NO
YES
NO
YES
NO
```