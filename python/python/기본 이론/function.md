함수를 정의할때 return값을 선언해주지 않으면 아무 값도 반환하지 않는다. 헷갈리지 말자

```python
def f(x):
	print(x+10)

f(10)
c = f(10)
print(c)
```

```text
20
20
None
```


#### sorted(args) vs .sort()

- sorted는 원본을 변형시키지 않는다.
-  sorted는 return값이 존재한다는것
- .sort() 함수는 원본을 변현시킨다. 그리고 return값이 없기때문에 화면에 아무것도 출력되지 않는다.

```python
>>> list_ex = [5,4,3,2,1]
>>> list_ex
[5,4,3,2,1]
>>> sorted(list_ex)
[1,2,3,4,5]
>>> list_ex
[5,4,3,2,1]
>>> list_ex.sort()
>>> list_ex
[1,2,3,4,5]
```

#### print()
- print()문은 return값이 없기 때문에 c에는 None이 저장된다.
```python
>>> >>> def f(x):
...   return print(x+10)
...
>>> f(10)
20
>>> c = f(10)
20
>>> c
>>>
```