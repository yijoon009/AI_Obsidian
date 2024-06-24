
### asterisk - unpacking a container
- tuple, dict등 자료형에 들어가있는 값을 unpacking
- 함수의 입력값, zip등에 유용하게 사용 가능
```python
def asterisk_test(a, *args):
    print(a, *args)
    print(a, args)
    print(type(args))

asterisk_test(2, *(2,3,4,5,6))
```

- 변수를 넣어주는 곳에서 `*(2,3,4,5,6)` 처럼 앞에 `*`을 사용했기 때문에 풀려서 값이 들어간다. 그래서 2,3,4,5,6 처럼 값이 풀려서 들어간다.
- `*args`는 가변인자기 때문에 여러 값을 받을 수 있고, 이걸 튜플로 받을 수 있다. 그래서 `args`를 출력하면 (2,3,4,5,6)으로 튜플로 묶어서 출력된다.

```
2 2 3 4 5 6
2 (2, 3, 4, 5, 6)
<class 'tuple'>
```

**변수 넣을때 `*` 사용 안하면 튜플값 하나로 인식된다.**

```python
def asterisk_test(a, *args):
    print(a, args)
    print(type(args))

test = (2,3,4,5,6)
asterisk_test(1, test)
```

```
1 ((2,3,4,5,6), )
<class 'tuple'>
```


### 함수 파라미터로 넣어주는 변수에서 `*` 사용과, 함수 선언에서 사용되는 `*`는 다른 역할이다.
- 함수를 사용하는 쪽에서 변수로 넣어주는 값에 `*`를 작성하면 언팩킹
- 함수를 선언한쪽에서 `*`를 사용하면 여러개를 받을 수 있는 가변인자라는 의미
