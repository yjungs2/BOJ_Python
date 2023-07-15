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