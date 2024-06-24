- 가변인자는 일반적으로 `*args` 를 변수명으로 사용
- 기존 parameter 이후에 나오는 값을 tuple로 저장

```python
def asterisk_test(a, b, *args):
	return a+b+sum(args)

print(asterisk_test(1,2,3,4,5))
```


### 키워드 가변 인자

```python
def kwards_test_1(**kwards):
	print(kwards)

kwards_test_1(first=3, second=5, third=2)
```


- 아래처럼 코드 작성하면 에러 발생
```python

def kwards_test_3(one, two=3, *args, **kwrds):
    print(one+two+sum(args))
    print(args)
    print(kwrds)
    
#5,6,7,8,9가 *args에 들어가고 나머지 first, second, third가 kwrds에 들어간다
print(kwards_test_3(3,4,5,6,7,8,9,first=3, second=4, third=6))  

# 마지막 10때문에 에러 발생
print(kwards_test_3(10,30,3,5,6,first=3, second=5, third=10, 10))

# 에러 발생
# one=10, two=300이 키워드 인자로 인식되기때문에 파라미터 순서에서 에러 발생
print(kwards_test_3(one=10,two=300,3,5,6,first=3, second=5, third=10, 10))

# 정상 실행
# *args는 안들어가도 에러 안남 
print(kwards_test_3(one=10,two=300,first=3, second=5, third=10, 10))

```

