
- 덧셈이랑 곱셈은 원본에 영향을 안주지만
- 원본에 영향을 주는 함수
	- .append()
	- .extend()
	- remove()
	- .sort()
- del color[0]
	- 이건 아예 주소값을 삭제하는거라 좀 다르긴 한데 그래도 삭제긴 함..

- python list에는 다양한 타입의 값들이 저장된다.
- a = ["color", 1, 0.2]
- color = ["red","yellow"]
- a[0] = color
- -> [["red","yellow"], 1, 0.2]

## 주소값

```python3
a = [1, 2, 3, 4, 5]
b = [5, 4, 3, 2, 1]
b = a

print("a:", a) # 출력: a: [1, 2, 3, 4, 5]
print("b:", b) # 출력: b: [1, 2, 3, 4, 5]
print(a is b) # 출력: True, a와 b가 동일한 객체를 가리키는지 확인
print(id(a)) # a의 메모리 주소 출력
print(id(b)) # b의 메모리 주소 출력
```

```plain
a: [1, 2, 3, 4, 5]
b: [1, 2, 3, 4, 5]
True
4368992640
4368992640
```

위 내용은 아예 주소값을 일치시키는거지만 그냥 데이터만 **복사**하고싶다면
❗️이 경우는 1 dimension 가능하고 2 dimension부터는 원본도 영향을 미친다!
	2 dimension에서는 import copy / copy.deepcopy() 를 사용해야 데이터값만 복사가 되는것

```python3
a = [5,4,3,2,1]
b = a[:]
a.sort()
print(a)
print(b)
```

```text
[1, 2, 3, 4, 5]
[5, 4, 3, 2, 1]
```

### 패킹, 언패킹
```python3
t = [1,2,3]
a, b, c = t
print(a)
print(b)
print(c)
```

```text
1
2
3
```