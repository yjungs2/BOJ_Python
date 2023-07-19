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

리스트 list() 관련 함수
```python
# 추가
li.append(x)
# 개수 세기
li.count(x)
```

집합 set() 관련 함수
```python
# 추가
s.add(x)
```

소수 출력
```python
# 소수점 일의 자리까지 출력
format((숫자), '.1f')

# print(f"{}")에서 바로 적용하기 (소수점 세자리 단위 출력)
print(f"{숫자:.3f}")
```

최대공약수와 최소공배수
```python
def gcd(a, b): # 조건 : a >= b
    if a % b == 0:
        return b
    else:
        return gcd(b, a%b)
```