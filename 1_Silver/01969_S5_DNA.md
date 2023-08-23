- 221218
## 백준 > Silver5 > 1969번 : DNA
메모리 30616kb 시간 92ms  
https://www.acmicpc.net/problem/1969  

코드
```python
n, m = map(int, input().split()) # DNA의 수 n, 문자열의 길이 m
sdna = [] # Hamming Distance 합이 가장 작은 DNA 원소 넣을 리스트
hdis = 0 # Hamming Distance 더할 변수
dna = [[0]*m for _ in range(n)] # m*n 크기의 배열
for i in range(n):
  dna[i] = list(input()) # n개의 DNA 저장
for j in range(m):
  atgc = {'A':0, 'C':0, 'G':0, 'T':0} # 뉴클레오티드 개수 셀 dict
  for k in range(n):
    if dna[k][j] == 'A':
      atgc['A'] += 1
    elif dna[k][j] == 'T':
      atgc['T'] += 1
    elif dna[k][j] == 'G':
      atgc['G'] += 1
    else:
      atgc['C'] += 1
  sorted_atgc = sorted(atgc.items(), key = lambda item:item[1], reverse=True) # 개수가 큰 순서대로 정렬
  sdna.append(sorted_atgc[0][0]) # 개수가 가장 많으면서, 사전순으로 앞서는 뉴클레오티드 저장
# print(sdna)
for i in range(n):
  for j in range(m):
    if dna[i][j] != sdna[j]: # 각 위치의 뉴클레오티드 문자가 다르다면
      hdis += 1 # Hamming Distance 1 증가
print("".join(sdna)) # Hamming Distance 합이 가장 작은 DNA 출력
print(hdis) # Hamming Distance의 합 출력
```

입력
```
5 8
TATGATAC
TAAGCTAC
AAAGATCC
TGAGATAC
TAAGATGT

4 10
ACGTACGTAC
CCGTACGTAG
GCGTACGTAT
TCGTACGTAA

6 10
ATGTTACCAT
AAGTTACGAT
AACAAAGCAA
AAGTTACCTT
AAGTTACCAA
TACTTACCAA
```

출력
```
TAAGATAC
7

ACGTACGTAA
6

AAGTTACCAA
12
```