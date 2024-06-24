- 데코레이터 자체에 인자를 전달하려면, 데코레이터를 한 단계 더 래핑(wrapping)해야 합니다. 즉, 인자를 받는 함수가 데코레이터를 반환하도록 해야 합니다.



```python
def generate_power(exponent):
    def wrapper(f):
        def inner(*args):
            result = f(*args)
            return exponent**result
        return inner
	inner(*args)
    return wrapper

@generate_power(2)
def raise_two(n):
    return n**2

```


