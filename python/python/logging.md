##### logging_example

```python
import logging

logging.debug('틀렸어')
logging.info('확인해')
logging.warning('조심해')
logging.error('에러났어')
logging.critical('망했다')
```

```
WARNING:root:조심해
ERROR:root:에러났어
CRITICAL:root:망했다
```

실제 출력은 waring, error, critical만 출력
기본적으로 파이썬 오퍼레이션 단계에서  warning 이상부터 출력하도록 설계되어있다.
이걸 수정하려면 logging level 수정 필요

```python
import logging

if __name__ == '__main__':
    logger = logging.getLogger('main')
    # python 3.7 이전
    # logging.setLevel(logging.INFO)
    # python 3.8 이후
    logging.basicConfig(level=logging.DEBUG)
        
    logging.debug('틀렸어')
    logging.info('확인해')
    logging.warning('조심해')
    logging.error('에러났어')
    logging.critical('망했다')
```

#### stream handler

```python
# stream handler는 my.log에 파일로 출력하겠다라는 내용
stream_handler = logging.FileHandler(
'my.log', mode='a', encoding='utf8')
logger.addHandler(stream_handler)
```


## 로그 설정 방법을 어디에 저장해놓느냐

1. configparser = 파일에 저장
2. argparser = 실행시점에


#### configparser

- 프로그램의 실행  설정을 file에 저장
- section, key, value값의 형태로 설정된 설정 파일 사용
- 설정파일을 Dict Type으로 호출 후 사용


- config file (example.cfg)
	- Section - 대괄호
	- 속성- key:value
```
[SectionOne]
Status: Single
Name: Derek
Value: Yes
Age: 30
Single: True

[SectionTwo]
FavoriteColor = Green

[SectionThree]
FamilyName: Johnson
```

- config_script.py

```python
import configparser

config = configparser.ConfigParser()
config.sections()

config.read('example.cfg')
print(config.sections())

for key in config['SectionOne']:
    value = config['SectionOne'][key]
    print(f'{key}: {value}')

# print(config['SectionOne']['Status'])
```

```
['SectionOne', 'SectionTwo', 'SectionThree']
status: Single
name: Derek
value: Yes
age: 30
single: True
```


#### argparser
- console창에서 프로그램 실행시 Setting 정보를 저장함
- 거의 모든 console 기반 python 프로그램 기본으로 제공
- 특수 모듈도 많이 존재하지만(TF), 일반적으로 argparse 사용
- command-line option이라고 부름

argparse_ex.py
```python
import argparse

parser = argparse.ArgumentParser(description='sum two integers')

parser.add_argument('-a', '--a_value', dest='a', help='A integers', type=int, required=True)
parser.add_argument('-b', '--b_value', dest='b', help='B integers', type=int, required=True)

args = parser.parse_args()
print(args)
print(args.a)
print(args.b)
print(args.a + args.b)
```

```
>>> python argparse_ex.py 
usage: argparse_ex.py [-h] -a A -b B
argparse_ex.py: error: the following arguments are required: -a/--a_value, -b/--b_value

>>> python argparse_ex.py -a 10 -b 39
Namespace(a=10, b=39)
10
39
49
```





