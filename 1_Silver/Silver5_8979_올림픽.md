- 230212
##  백준 > Silver5 > 8979번 : 올림픽
메모리 31256kb 시간 88ms  
https://www.acmicpc.net/problem/8979  

코드
```python
n, k = map(int, input().split()) # 국가 수 n, 등수 알고 싶은 국가 k
medal = dict()
for _ in range(n):
  nums = list(map(int, input().split()))
  medal[nums[0]] = (nums[1], nums[2], nums[3]) # 국가 번호 key, (금, 은, 동) value
std = medal[k] # 등수 알고 싶은 국가의 메달 정보
ans = 0
for i in medal: # 각 나라들이
  if medal[i] > std: # 국가 k보다 메달이 많다면
    ans += 1 # 자신보다 더 잘한 나라 개수 증가
print(ans + 1) # 국가 k의 등수 출력 : (자신보다 더 잘한 나라 수 + 1)
```

입력
```
4 3
1 1 2 0
2 0 1 0
3 0 1 0
4 0 0 1

4 2
1 3 0 0
3 0 0 2
4 0 2 0
2 0 2 0
```

출력
```
2

2
```