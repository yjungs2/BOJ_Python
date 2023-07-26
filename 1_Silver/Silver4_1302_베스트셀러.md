- 221224
## 백준 > Silver4 > 1302번 : 베스트셀러
메모리 30616kb 시간 36ms  
https://www.acmicpc.net/problem/1302  

코드
```python
n = int(input()) # 팔린 책의 개수
nameli = [] # 책의 제목 리스트
books = dict() # 책의 제목과 수량 딕셔너리
for _ in range(n):
  name = input() # 입련된 책의 제목
  if name in nameli: # 입력된 책이 리스트에 존재한다면
    books[name] += 1 # 개수 추가
  else: # 입력된 책이 리스트에 존재하지 않는다면
    books[name] = 1 # 딕셔너리에 해당 책 추가
  nameli.append(name) # 리스트에 추가하기
sorted_books = sorted(books.items(), key=lambda item:item[1], reverse=True) # 수량 내림차순으로 정렬
# print(sorted_books)
# [('icecream', 2), ('peanuts', 2), ('chocolate', 2), ('candy', 1), ('apple', 1)]
ansli = [sorted_books[0][0]] # 정렬된 딕셔너리의 첫 번째 책 담기
for i in range(1, len(sorted_books)):
  if sorted_books[i][1] == sorted_books[i-1][1]: # 수량이 앞의 책의 수량과 동일하다면
    ansli.append(sorted_books[i][0]) # 리스트에 추가
  else: # 수량이 줄었다면
    break # 리스트에 추가할 필요 없으니 중단하기
ansli.sort() # 가장 많이 팔린 책들을 오름차순 정렬
# print(ansli)
# ['chocolate', 'icecream', 'peanuts']
print(ansli[0]) # 가장 많이 팔린 책 중 사전 순으로 가장 앞서는 제목 출력
```

입력
```
8
icecream
peanuts
peanuts
chocolate
candy
chocolate
icecream
apple
```

출력
```
chocolate
```