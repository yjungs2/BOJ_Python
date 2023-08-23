- 220623
##  백준 > Bronze1 > 9093번 : 단어 뒤집기
메모리 30840kb 시간 1132ms  
https://www.acmicpc.net/problem/9093  

코드
```python
t = int(input()) # 테스트 케이스 개수 t
for i in range(t):
    sen = list(input().split(' ')) # 입력으로 주어진 문장 -> 단어를 리스트에 담음
    resen = [] # 주어진 문장의 단어를 모두 뒤집어 담을 리스트
    for n in sen:
        resen.append(n[::-1]) # 문장의 단어를 뒤집음
    print(" ".join(resen)) # 리스트를 띄어쓰기 있는 문자열로 합침
```

입력
```
2
I am happy today
We want to win the first prize
```

출력
```
I ma yppah yadot
eW tnaw ot niw eht tsrif ezirp
```