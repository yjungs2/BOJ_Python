- 230219
##  백준 > Bronze1 > 17283번 : I am Groot
메모리 31256kb 시간 40ms  
https://www.acmicpc.net/problem/17283   

코드
```python
l = int(input()) # 중심 줄기 길이 l
r = int(input()) # 비율 r
ans = 0
n = 1 # n번째 가지
length = l
while(int(length*(r/100)) > 5): # 다음 나뭇가지 길이가 5 이하면 반복문 중단
  length = int(length*(r/100)) # 다음에 자라는 나뭇가지 길이
  ans += length*(2**n) # 나뭇가지 길이 * 나뭇가지 개수 만큼 더하기
  n += 1 # 횟수 증가
print(int(ans)) # 중심 줄기를 제외한 나뭇가지 총 길이 정수만 출력
```

입력
```
500
30
```

출력
```
584  
# 1번째 가지의 길이는 ⌊500 × (30/100)⌋ = 150  
# 2번째 가지의 길이는 ⌊150 × (30/100)⌋ = 45  
# 3번째 가지의 길이는 ⌊45 × (30/100)⌋ = 13  
# 4번째 가지의 길이는 ⌊13 × (30/100)⌋ = 3.9 이고, 5cm 이하라서 자라지 않음.  
# 총 길이의 합은 2×150 + 4×45 + 8×13 = 584cm
```