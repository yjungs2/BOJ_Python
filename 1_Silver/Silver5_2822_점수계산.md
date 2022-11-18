- 220704
##  백준 > Silver5 > 2822번 : 점수 계산
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/2822  

코드
```python
score = [0] * 8 # 총 8개 문제
for i in range(8):
    score[i] = int(input()) # 참가자의 8개 문제 점수

hisum = 0
hinum = []
for j in range(5): # 가장 높은 점수 5개
    hinum.append(score.index(max(score)) + 1) # 문제 번호 (1부터 시작)
    hisum += max(score) # 최고점
    score[score.index(max(score))] = 0 # 최고점 리셋
hinum.sort() # 오름차순 정렬
print(hisum) # 참가자의 총점
print(hinum[0], hinum[1], hinum[2], hinum[3], hinum[4]) #최종 점수에 포함되는 문제 번호
```

```
*index*
리스트.index(찾고자 하는 원소) 코드를 통해 특정 원소의 인덱스 값을 찾아낼 수 있다.
위 문제처럼 리스트 안에서 가장 큰 값의 인덱스 번호를 쉽게 찾을 수 있다.
```

입력
```
20
30
50
48
33
66
0
64
```

출력
```
261
3 4 5 6 8
```