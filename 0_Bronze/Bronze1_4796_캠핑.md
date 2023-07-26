- 221229
## 백준 > Bronze1 > 4796번 : 캠핑
메모리 30616kb 시간 88ms  
https://www.acmicpc.net/problem/4796  

```
5 8 17일 때 11 (=5x2+1)  
5 8 20일 때 14 (=5x2+4)  
5 8 23일 때 15 (=5x2+5)의 경우의 수를 고려해서 코드를 짰다.
```

코드
```python
time = 0
while True:
  time += 1 # 케이스 번호
  l, p, v = map(int, input().split()) # 연속하는 p일 중 l일 동안 사용 가능, v일짜리 휴가
  if l==0 and p==0 and v==0: # 중단 조건
    break
  else:
    ans = l*(v//p) + min(v%p, l) # 캠핑장을 사용할 수 있는 최대 일수 계산
    print(f"Case {time}: {ans}")
```

입력
```
5 8 20
5 8 17
5 8 23
5 8 24
0 0 0
```

출력
```
Case 1: 14
Case 2: 11
Case 3: 15
Case 4: 15
```