
파이썬의 객체는 원레 '**메모리**'에 있어야 한다. 그래서 파이썬 코드를 실행했을때 순간적으로 메모리에 올라가는 작업이 있다.

파이썬 인터프리터가 종료되면 메모리도 사라진다. 즉, 객체도 사라진다.

- 파이썬의 객체를 영속화(persistence)하는 built-in 객체
- 데이터, object 등 실행중 정보를 저장 -> 불러와서 사용
- 저장해야하는 정보, 계산 결과(모델) 등 활용이 많음

#### pickle dump

```python
import pickle

f = open('list.pickle', 'wb')  # pickle은 파이썬에 특화된 바이너리 파일
test = [1,2,3,4,5]
pickle.dump(test, f)     # test를 f라는 저장소에 저장한다.
f.close
```


#### pickle read
```python
f = open('list.pickle', 'rb')     # read binary
test_pickle = pickle.load(f)
print(test_pickle)
f.close
```