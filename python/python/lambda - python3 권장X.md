```python
def f(x, y):
	return x+y
print(f(1,5))
```

```python
f = lambda x, y: x+y
print(f(1,5))
```

```python
(lambda x, y: x+y)(10,50)
```

```
up_low = lambda x: "-".join(x.split())
print(up_low("my happy"))
```