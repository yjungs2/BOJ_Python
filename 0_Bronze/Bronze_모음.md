예외처리 (try-except 사용하기)
```python
while True:
    try:
        # 실행할 코드
    except:
        break # 예외가 발생했을 때 처리하는 코드
```

ord()와
```python
# 영어 소문자
# ord('a') = 97 ~ ord('z') = 122
# 영어 대문자
# ord('A') = 65 ~ ord('Z') = 90
ord()
chr()
```

대문자 <-> 소문자
```python
# 문자 모두 대문자로
str.upper()
# 문자 모두 소문자로
str.lower()
# 대문자 소문자 현재와 반대로

```

int를 str로 바꿔서 join하여 출력
```python
print(" ".join(map(str, num))) # 공백으로 구분한 숫자 출력
```

끊어 출력하기
```python
print(word[i], end="\n") # 출력 후 줄내림
print(word[i], end='') # 공백 없이 이어서 출력
```

time()
```python
import time
start = time.time()
# 코드
end = time.time()
print(end - start)
```

반올림 / 올림 / 내림
```python
# 반올림
round
# 내림
int
```

정수 판별
```python
x.isdigit() # True/False
```

소수점 형식으로 출력
```python
# 소수점 일의 자리까지 출력
format((숫자), '.1f')

# print(f"{}")에서 바로 적용하기 (소수점 세자리 단위 출력)
print(f"{숫자:.3f}")
```

소수(prime number) 판별
```python
def is_prime(x):
  for i in range(2, int(num**0.5)+1):
    if x%i == 0:
      return False
  return True
```

최대공약수와 최소공배수
```python
# 최대공약수 함수 정의
def gcd(a, b): # 조건 : a >= b
    if a % b == 0:
        return b
    else:
        return gcd(b, a%b)

print(gcd(a,b)) # 최대공약수
print(a*b//gcd(a,b)) # 최소공배수
```

최빈값 Counter
```python
from collections import Counter

nums = [1,3,8,-2,2,3,8,6,6]
nums.sort()
cnt = Counter(nums).most_common()
print(cnt) # [(3, 2), (6, 2), (8, 2), (-2, 1), (1, 1), (2, 1)]
```

리스트 list() 관련 함수
```python
# 추가
li.append(x)
# 개수 세기
li.count(x)
# 특정 값을 가진 인덱스 찾기
li.index(값)
```

집합 set() 관련 함수
```python
# 추가
s.add(x)
```

딕셔너리 dict() 관련 함수
```python
# 딕셔너리 key 기준 정렬
sorted_dic = sorted(dic.items(), key=lambda item:item[0]) # key 오름차순 정렬
sorted_dic = sorted(dic.items(), key=lambda item:item[0], reverse=True) # key 내림차순 정렬
# 딕셔너리 value 기준 정렬
sorted_dic = sorted(dic.items(), key=lambda item:item[1]) # value 오름차순 정렬
sorted_dic = sorted(dic.items(), key=lambda item:item[1], reverse=True) # value 내림차순 정렬
```

런타임 에러 해결하기
```python
# 런타임에러 (RecursionError)
import sys
sys.setrecursionlimit(10**6) # 재귀 깊이를 늘리는 코드

```