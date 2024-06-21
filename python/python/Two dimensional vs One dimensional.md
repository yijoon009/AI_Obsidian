```python
case_1 = ["A", "B", "C"]
case_2 = ["D", "E", "A"]
result = [i+j for i in case_1 for j in case_2]
print(result)
-> ['AD', 'AE', 'AA', 'BD', 'BE', 'BA', 'CD', 'CE', 'CA']
result = [[i+j for i in case_1] for j in case_2] # for j in case_2 먼저 실행
print(result)
-> [['AD', 'BD', 'CD'], ['AE', 'BE', 'CE'], ['AA', 'BA', 'CA']]
```

- result = [[i+j for i in case_1] for j in case_2]
	- for j in case_2가 먼저 실행된다.

```python
for j in case_2:
	line = []
	for i in case_1:
		line.append(i+1)
```