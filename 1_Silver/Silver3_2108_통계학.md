- 221216
## 백준 > Silver3 > 2108번 : 통계학
메모리 53688kb 시간 456ms  
https://www.acmicpc.net/problem/2108  

**최빈값**을 출력하기 위해 **Counter.most_common()** 사용
```python
from collections import Counter

nums = [1,3,8,-2,2,3,8,6,6]
nums.sort()
cnt = Counter(nums).most_common()
print(cnt) # [(3, 2), (6, 2), (8, 2), (-2, 1), (1, 1), (2, 1)]
```

코드
```python
import sys
input = sys.stdin.readline

from collections import Counter

n = int(input()) # 수의 개수
nums = []
nsum = 0
for _ in range(n):
  num = int(input())
  nums.append(num) # 리스트에 정수 추가
  nsum += num # 정수들의 합 계산
nums.sort() # 오름차순 정렬
cnt = Counter(nums).most_common() # 정수의 count 리스트
print(round(nsum/n)) # (1) 산술평균 출력 (소수점 첫째 자리에서 반올림)
print(nums[(n-1)//2]) # (2) 중앙값 출력
if len(cnt) == 1: # 수의 개수가 1이라면
  print(cnt[0][0]) # 그 수 출력
else:
  if cnt[0][1] == cnt[1][1]: # 최빈값이 여러개라면
    print(cnt[1][0]) # (3) 최빈값 중 두 번째로 작은 값 출력
  else:
    print(cnt[0][0]) # 최빈값이 하나라면 최빈값 출력
print(nums[-1] - nums[0]) # (4) 범위 출력
```

입력
```
# 예제 1
5
1
3
8
-2
2

# 예제 2
1
4000

# 예제 3
5
-1
-2
-3
-1
-2

# 예제 4
3
0
0
-1
```

출력
```
# 예제 1
2
2
1
10

# 예제 2
4000
4000
4000
0

# 예제 3
-2
-2
-1
2

# 예제 4
0
0
0
1
```