### Attribute
- Attribute 추가는 `__init__`, self와 함께
- `__init__`은 객체 초기화 예약 함수

```python
class SoccerPlayer(object):
	def __init__(self, name, position, back_naumber):
		self.name = name
		self.position = position
		self.back_number = back_number
	
```

### self
- def에 선언된 self는 '생성된 instance'를 의미