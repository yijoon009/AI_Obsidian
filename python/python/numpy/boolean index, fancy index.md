## boolean index

- 특정 조건에 따른 값을 배열 형태로 추출
- Comparison operation 함수들도 모두 사용 가능
- 


```python
a = np.array([1,4,0,2,3,8,9,7], float)
a > 3
-> array([False,  True, False, False, False,  True,  True,  True])

# 조건이 true인 index의 element만 추출
a[a>3]
array([4., 8., 9., 7.])

# 보통 condition이란 이름으로 뽑아서 사용한다.
condition = a < 3
a[condition]
```


## fancy index

- numpy는 array를 index value로 사용해서 값 추출

```python
a = np.array([2,4,6,8], float)
b = np.array([0,0,1,3,2,1], int)   # 반드시 integer로 선언
a[b]      # bracket index, b 배열의 값을 index로 하여 a의 값들을 추출
-> array([2., 2., 4., 8., 6., 4.])
```


## 둘의 차이
- boolean index는 boolean list 사용, fancy index는 integer list 사용
- boolean index는 기존 값과 비교대상의 shape이 같아야하는데, fancy list는 그럴 필욘 없다.