- 220605
##  백준 > Bronze2 > 8958번 : OX퀴즈
메모리 30840kb 시간 88ms  
https://www.acmicpc.net/problem/8958  

코드
```python
t = int(input()) # 테스트 케이스 개수
for i in range(t):
    answer = 0
    a = list(input()) # 입력받는 문자열 리스트
    b = [0] * len(a) # 점수 넣을 리스트 생성
    for j in range(len(a)): # 문자열 길이만큼 돌면서
        if j == 1: # 첫 번째 원소
            if a[j] == 'O':
                b[j] = 1
        if a[j] == 'O': # 나머지 원소
            b[j] = b[j-1] + 1
    for k in b: # 점수의 합
        answer += k
    print(answer)
```

입력
```
5
OOXXOXXOOO
OOXXOOXXOO
OXOXOXOXOXOXOX
OOOOOOOOOO
OOOOXOOOOXOOOOX
```

출력
```
10
9
7
55
30
```