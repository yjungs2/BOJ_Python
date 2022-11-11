- 220609
##  백준 > Bronze2 > 1100번 : 하얀 칸
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/1100  

코드
```python
arr = [list(input()) for i in range(8)] # 체스판의 상태 입력받음
answer = 0 # 하얀 칸 위에 있는 말의 개수
for r in range(8):
    for c in range(8):
        # 행렬 arr의 인덱스 r과 c의 합이 짝수면 하얀 칸
        if (r+c)%2 == 0:
            if 'F' in arr[r][c]:
                answer += 1
print(answer)
```

입력
```
.F.F...F
F...F.F.
...F.F.F
F.F...F.
.F...F..
F...F.F.
.F.F.F.F
..FF..F.
```

출력
```
1
```