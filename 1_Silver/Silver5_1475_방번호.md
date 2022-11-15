- 220629
##  백준 > Silver5 > 1475번 : 방 번호
메모리 30840kb 시간 76ms  
https://www.acmicpc.net/problem/1475  

코드 (처음 아이디어)
```python
# 틀렸습니다
n = list(input())
num = [0] * 10
for i in n:
    num[int(i)] += 1
if max(num) == num[6] or max(num) == num[9]:
    if (num[6] + num[9]) % 2 == 0:
        print((num[6] + num[9]) // 2)
    else:
        print((num[6] + num[9]) // 2 + 1)
else:
    print(max(num))
# (반례) 9999333 -> 답 : 3 이지만 2 출력
```

코드 (최종)
```python
n = list(input())
num = [0] * 10
for i in n:
    if int(i) == 9: # 숫자 6과 9를 같은 인덱스에 넣어줌
        num[6] += 1
    else:
        num[int(i)] += 1
if num[6] % 2 == 0: # 숫자 6과 9의 총 개수가 짝수개이면
    num[6] = num[6] // 2 # 그 절반만큼 필요
else: # 숫자 6과 9의 총 개수가 홀수개이면
    num[6] = num[6] // 2 + 1 # 절반 + 1 만큼 필요
print(max(num))
```

```
숫자 6과 9의 경우에 따라 필요한 카드 수를 num 리스트에서 아예 수정한 뒤에
리스트의 최댓값을 출력하는 방식으로 코드를 짰다.
```

입력
```
9999

122

12635

888888

9999333
```

출력
```
2

2

1

6

3
```