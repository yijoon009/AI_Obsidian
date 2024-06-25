```
import os
os.mkdir('log')
```

```python
try:
	os.mkdir('abc')
except FileExistsError as e:
	print('already created')
```

```python
os.path.exists('abc')
-> True
```

```python
os.path.isfile('file.ipynb')
-> True
```

### 경로
```python
import shutil

source = 'i_have_a_dream.txt'
dest = os.path.join('abc', 'kim.txt')
print(dest)
-> 'abc/kim.txt'
shutil.copy(source, dest)   # 파일 복사 함수
```

### pathlib

최근에는 pathlib 모듈을 사용해서 path를 객체로 다룸

```python
import pathlib

cwd = pathlib.Path.cwd()
print(cwd)
-> /Users/yjkim/study/python/PY4E

print(cwd.parent)
-> /Users/yjkim/study/python

print('>>>', list(cwd.parents))
print('<<<', list(cwd.glob('*')))

```

```
>>> [PosixPath('/Users/yjkim/study/python'), PosixPath('/Users/yjkim/study'), PosixPath('/Users/yjkim'), PosixPath('/Users'), PosixPath('/')]
<<< [PosixPath('/Users/yjkim/study/python/PY4E/pythonic'), PosixPath('/Users/yjkim/study/python/PY4E/file'), PosixPath('/Users/yjkim/study/python/PY4E/variable'), PosixPath('/Users/yjkim/study/python/PY4E/matplotlib_ex.py'), PosixPath('/Users/yjkim/study/python/PY4E/tqdm_ex.py'), PosixPath('/Users/yjkim/study/python/PY4E/oop'), PosixPath('/Users/yjkim/study/python/PY4E/game'), PosixPath('/Users/yjkim/study/python/PY4E/function'), PosixPath('/Users/yjkim/study/python/PY4E/unpacking_zip.py'), PosixPath('/Users/yjkim/study/python/PY4E/README.md'), PosixPath('/Users/yjkim/study/python/PY4E/variable.py'), PosixPath('/Users/yjkim/study/python/PY4E/command_data.csv'), PosixPath('/Users/yjkim/study/python/PY4E/structor'), PosixPath('/Users/yjkim/study/python/PY4E/condition'), PosixPath('/Users/yjkim/study/python/PY4E/list'), PosixPath('/Users/yjkim/study/python/PY4E/format'), PosixPath('/Users/yjkim/study/python/PY4E/asterisk.py'), PosixPath('/Users/yjkim/study/python/PY4E/.git'), PosixPath('/Users/yjkim/study/python/PY4E/unpacking.py')]
```


