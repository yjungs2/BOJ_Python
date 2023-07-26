- 221221
## 백준 > Bronze2 > 2592번 : 대표값
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/2592  

코드
```python
nums = [] # 수 담을 리스트
ndic = dict() # 수 개수 체크할 딕셔너리
for _ in range(10): # 첫째 줄부터 열 번째 줄까지
  num = int(input()) # 한 줄에 하나씩 자연수 주어짐
  if num in nums: # 전에 있던 수라면
    ndic[num] += 1 # 딕셔너리 개수 증가
  else: # 전에 없던 수라면
    ndic[num] = 1 # 딕셔너리에 해당 수 추가
  nums.append(num) # 리스트에 수 담기
  sorted_ndic = sorted(ndic.items(), key=lambda item:item[1], reverse=True) # 최빈값 순대로 정렬
#print(nums)
#print(sorted_ndic)
print(sum(nums)//10) # 평균 출력
print(sorted_ndic[0][0]) # 최빈값 출력
```

입력
```
10
40
30
60
30
20
60
30
40
50
```

출력
```
37
30
```