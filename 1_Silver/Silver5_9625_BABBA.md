- 220705
##  백준 > Silver5 > 9625번 : BABBA
메모리 30840kb 시간 68ms  
https://www.acmicpc.net/problem/9625  

코드
```python
k = int(input()) # 버튼 누르는 횟수
cnta = [1] # 'A'로 시작
cntb = [0]
for i in range(k): # k번 버튼 누름
    cnta.append(cntb[i])
    cntb.append(cnta[i] + cntb[i])
print(cnta[k], cntb[k])
```

규칙
```
(1)
abstr = 'A'로 두고
k번 만큼 abstr을 돌면서 'A'는 'B'로 / 'B'는 'AB'로 replace 한다.
이후, abstr.count('A')와 abstr.count('B')로
문자 내의 'A'와 'B'의 개수를 찾으려고 했다.
but, 
처음 생각한 방법이 뜻대로 되지 않아 두 번째 생각한 방법으로 해결

(2)
무조건 'A'로 시작하니
버튼을 누를 때마다 'A'와 'B'의 개수가 어떻게 변화하는지 직접 세어보았다.
거기서 발견한 규칙으로 cnta 배열과 cntb 배열에 새로운 값을 append로 추가하여
원하는 k번째 인덱스에 해당하는 값을 불러온다.
```
[9625번](./Image/9625.jpg)
```
K번째 A의 개수는 (K-1)번째 B의 개수이고,
K번째 B의 개수는 (K-1)번째 A의 개수와 B의 개수의 합이라는
규칙을 가지고 있음을 알 수 있다.
```

입력
```
10
```

출력
```
34 55
```