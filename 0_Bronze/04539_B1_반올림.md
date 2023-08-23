- 230204
##  백준 > Bronze1 > 4539번 : 반올림
메모리 31256kb 시간 40ms  
https://www.acmicpc.net/problem/4539  

코드
```python
import sys
input = sys.stdin.readline

n = int(input()) # 테스트 케이스 개수 n
for _ in range(n):
  x = list(map(int, input().rstrip())) # 입력된 정수 x(숫자 문자열)를 리스트에 숫자로 넣기
  # 여기서 rstrip()을 안 해주면 런타임 에러(ValueError)가 발생한다.
  if len(x) == 1: # 한 자리 수라면
    print(x[0]) # 그대로 출력
  else: # 두 자리 이상의 수라면
    for i in range(len(x)-1, 0, -1): # 일의 자리부터
      if x[i] >= 5: # 해당 자리의 수가 5 이상이면
        x[i-1] = x[i-1] + 1 # 해당 앞 자리 반올림하기
      x[i] = 0 # 해당 자리 수 0으로 변경
    print(int("".join(map(str, x)))) # 반올림한 결과 출력
```

입력
```
9
15
14
4
5
99
12345678
44444445
1445
446

1
105
```

출력
```
20
10
4
5
100
10000000
50000000
2000
500

100
```