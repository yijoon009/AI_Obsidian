## Read

read() txt 파일 안에 있는 내용을 문자열로 반환

```python
f = open('i_have_a_dream.txt', 'r')
contents = f.read()
print(contents)
f.close()
```


with 구문과 함께 사용
```python
with open('i_have_a_dream.txt', 'r') as my_file:
	contents = my_file.read()
	# contents = my_file.readlines()  # 파일 전체를 list로 반환
	print(type(contents), contents)
```


## Write

mode는 'W', encoding='utf8;
```python
f = open('count_log.txt','w', encoding='utf8')
for i in range(1, 11):
	data = '%d번째 줄입니다.\n' % i
	f.write(data)
f.close()
```

mode 'a'는 추가모드
```python
with open('count_log.txt','a', encoding='utf8') as f:
	for i in range(1, 11):
		data = '%d번째 줄입니다.\n' % i
		f.write(data)
```