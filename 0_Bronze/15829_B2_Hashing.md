- 230222
##  백준 > Bronze2 > 15829번 : Hashing
메모리 31256kb 시간 40ms  
https://www.acmicpc.net/problem/15829  

코드
```python
l = int(input()) # 문자열 길이 l
word = input() # 영문 소문자로 이루어진 문자열
ans = 0
for i in range(len(word)):
  ans += (ord(word[i])-96)*(31**i) # 해시 값 계산
print(ans%1234567891) # mod M 적용해서 출력
```

입력
```
5
abcde

3
zzz

1
i
```

출력
```
4739715
# 1 × 31^0 + 2 × 31^1 + 3 × 31^2 + 4 × 31^3 + 5 × 31^4 = 1 + 62 + 2883 + 119164 + 4617605 = 4739715

25818
# 26 × 31^0 + 26 × 31^1 + 26 × 31^2 = 26 + 806 + 24986 = 25818

9
```