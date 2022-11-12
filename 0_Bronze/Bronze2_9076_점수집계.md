- 220613
##  백준 > Bronze2 > 9076번 : 점수 집계
메모리 30840kb 시간 64ms  
https://www.acmicpc.net/problem/9076  

코드
```python
t = int(input()) # 테스트 케이스 개수
for i in range(t):
    score = list(map(int, input().split())) # 점수 리스트 생성
    score.sort() # 오름차순 정렬
    if score[3] - score[1] >= 4: # 최고점과 최저점의 차이가 4점 이상이면
        print("KIN") # 점수 조정 거치므로 KIN(Keep In Negotiation) 출력
    else: # 아니라면
        print(score[1] + score[2] + score[3]) # 점수 총점 출력
```

입력
```
4
10 8 5 7 9
10 9 10 9 5
10 3 5 9 10
1 2 3 6 9
```

출력
```
24
28
KIN
KIN
```