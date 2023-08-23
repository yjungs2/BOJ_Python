- 221117
## 백준 > Silver5 > 11004번 : K번째 수
메모리 622580kb 시간 4288ms  
https://www.acmicpc.net/problem/11004

코드
```python
n, k = map(int, input().split(" "))
nums = list(map(int, input().split(" ")))
nums.sort() # 오름차순 정렬
print(nums[k-1]) # 앞에서부터 K번째 있는 수를 출력
```

입력
```
5 2  
4 1 2 3 5
```

출력
```
2
```