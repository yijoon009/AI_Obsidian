
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

```
2 2 3 4 5 6
2 (2, 3, 4, 5, 6)
<class 'tuple'>
```