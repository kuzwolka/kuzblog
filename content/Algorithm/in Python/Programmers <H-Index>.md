---
publish: "true"
title: "Programmers: H-Index"
date: 2025-09-17
tags:
  - Python
  - Algorithm
  - Sorting
---
[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/42747)
### 문제 이해
- H-Index = 과학자의 성능 지표
- 논문 n편 중 h번 이상 인용된 논문이 h편 이상이고 나머지 논문이 h번 이하 인용 됐을 경우 해당 h의 최대값이 바로 H-Index
	- **h값은 주어지는 논문의 인용수를 따를 필요가 없음!**
- 논문 인용수가 입력으로 주어짐
---
### 문제 풀이
```python
def solution(citations):
	# 1. 내림차순 정렬
	citations.sort(reverse=True)
	print(citations)
    
	# 2. 인덱스 번호와 h값 비교
	for i, citation in enumerate(citations):
		if i+1 > citation:
			return i
	return len(citations)
```
- `i+1`은 `citation` 이상으로 인용된 논문 수
	- `citations = [6, 5, 3, 1, 0]`
	- `i` = 0일 경우: 1 > 6
	- `i` = 1일 경우: 2 > 5
	- `i` = 2일 경우: 3 > 3
	- `i` = 3일 경우: 4 > 1
- `return len(citations)`는 모든 논문의 인용수가 동일할 경우를 위해
---
### Syntax
**`enumerate(iterable, start=0)`**
- iteration에 대해 index와 해당 index의 값을 함께 return함
- 입력
	- `iterable`: iteration이 가능한 sequence 타입 데이터, iterator 등을 받음
		- ex) list, tuple, range 등
	- `start`: index의 시작점
- 구현
	```python
	def enumerate(iterable, start=0):
		# index 시작점 설정
		n = start
		# iteration
		for element in iterable:
			# yield를 통해 결과 출력
			yield n, element
			n += 1
	```