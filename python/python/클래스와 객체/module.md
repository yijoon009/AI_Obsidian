
example.py
```python
def function():
	return 'hello'

if __name__ == '__main__':
	test = 'GGG'
	print(test)
```

- `if __name__ == '__main__':`
	- 이렇게 해줘야 import example 하자마자 test가 프린트되는 상황을 막을 수 있다.

```python
def function():
	return 'hello'

test = 'GGG'
print(test)
```

- 위 코드처럼 해버리면 python shell에서 import example.py 하자마자 GGG가 출력된다.