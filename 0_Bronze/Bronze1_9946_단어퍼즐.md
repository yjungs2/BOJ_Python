- 230102
## 백준 > Bronze1 > 9946번 : 단어 퍼즐
메모리 30616kb 시간 1184ms  
https://www.acmicpc.net/problem/9946  

코드
```python
casenum = 0
while(True):
  first = input() # 처음 완성한 단어
  second = input() # 떨어뜨린 다음 회수한 알파벳
  if first == 'END' and second == 'END': # 중단 조건
    break
  else:
    casenum += 1 # 케이스 번호
    firstli = list(first) # 리스트에 담아
    secondli = list(second)
    firstli.sort() # 오름차순 정렬
    secondli.sort()
    if firstli == secondli: # 알파벳을 제대로 회수했다면
      print(f"Case {casenum}: same")
    else: # 알파벳을 잘못 회수했다면
      print(f"Case {casenum}: different")
```

입력
```
testing
intestg
abc
aabbbcccc
abcabcbcc
aabbbcccc
abc
xyz
END
END
```

출력
```
Case 1: same
Case 2: different
Case 3: same
Case 4: different
```