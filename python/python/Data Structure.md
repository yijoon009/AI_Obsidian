- push를 append()로, pop을 pop()으로
- .pop()
	- return을 하면서 원본 변경
	- sort는 return이 없는 대신 원본 변경, sorted는 return을 해주고 원본 번경X

### Stack

```python
word = input('enter your word: ')
word_list = list(word)
# print(word_list)
for i in range(len(word_list)):
	print(word_list.pop())
	print(word_list)
```

```text
enter your word: naver
['n', 'a', 'v', 'e', 'r']
r
['n', 'a', 'v', 'e']
e
['n', 'a', 'v']
v
['n', 'a']
a
['n']
n
[]
```
### Queue

```python
a = [1,2,3,4,5]
a.append(10)
a.append(20)
print(a.pop(0))
print(a.pop(0))
```

```
1
2
```


### Tuple
- 값의 변경이 불가능한 리스트
- 선언시 []이 아닌 () 사용
- 하나의 값으로 선언할때는 무조건 콤마 붙여야함
```python
t = (1)
type(t)
int
tt = (1,)
type(t)
tuple
```

### Set
- 값을 순서없이 저장, 중복 불허하는 자료형
- set 객체 선언을 이용해 객체 생성
```python
s = set([1,2,1,2,3])
print(s)
{1,2,3}
ss = {1,2,3,4,5}
type(ss)
set
```

- .add()
- .remove()

### Dictionary
- key와 value를 매칭하여 key로 value를 검색
- {key1:value1, key2:value2,,,}
- .items() : dict 데이터 출력 (각각의 아이템 type은 tuple)
- .keys(): 키 값만 출력
- .values(): value만 출력
- dict_ex["key1"] = value1 <- dict 추가
- 언패킹
```python
for k, v in country_code.items():
	print(k)
	print(v)
```
- "Korea" in country_code.keys() : key값에 Korea가 있는지 확인
- 82 in country_code.values() : value값에 82가 있는지 확인

### Collections

#### deque
- stack과 queue를 지원
- list에 비해 빠른 자료저장 방식
- rotate, reverse등 linked list의 특성을 지원함
```python
from collections import deque

deque_list = deque()
for i in range(5):
	deque_list.append(i)
```

#### defaultdict
- dict type의 값에 기본 값을 지정, 신규값 생성시 사용하는 방법
```python
d = dict()
print(d["first"])
-> keyError: 'first'
```

```python
from collections import defaultdict

d = defaultdict(object) # default dectionary를 생성
d = defaultdict(lambda: 0) # default 값을 0으로 설정
print(d["first"])
```

#### Counter
- sequence type의 data element들의 갯수를 dict 형태로 반환
```python
from collections import Counter
c = Counter()
c = Counter("gallahad")
print(c)
-> Counter({'a': 3, 'l': 2, 'g': 1, 'h': 1, 'd': 1})
```

```python
c = Counter({'red':4, 'blue':6})
print(list(c.elements()))
-> ['red', 'red', 'red', 'red', 'blue', 'blue', 'blue', 'blue', 'blue', 'blue']
```