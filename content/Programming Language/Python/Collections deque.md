---
draft: "true"
title:
date:
tags:
---
### 사용 방법
```python
from collections import deque

# 비어있는 deque 만들기
my_queue = deque()

# 데이터 추가
my_queue.append((0, 0, 1))
my_queue.append((0, 1, 2))
print("현재 큐:", my_queue)

current_position = my_queue.popleft()
print("꺼낸 데이터:", current_position)
print("남은 큐:", my_queue)
```