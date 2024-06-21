### yield(메모리 주소 절약)
- yield는 generator 형태. 호출할때 데이터를 출력해준다. 
- yield는 메모리 주소값만 갖고 있다가 호출될때 데이터를 반환한다.

```python
import sys

def generator_list(value) :
    result = []
    for i in range(value):
        result.append(i)
    return result


result = generator_list(50)
print(sys.getsizeof(result))
-> 472
```

```python
import sys

def generator_list(value) :
    result = []
    for i in range(value):
        yield i

result = generator_list(50)
print(sys.getsizeof(result))
-> 208
```

