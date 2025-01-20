### Section6. 함수(클래스, 메서드,  패키지)

<br>

### 함수 Function

```python
# 함수 
def hello():
  pass

def hello(name):
  return f'{name}야 안녕'
 
 hello('오즈')
 
 # result
 # 오즈야 안녕
```

<br>

### 함수 연습문제

```python
# 연습문제 2
# 정수 3개를 입력받아 평균을 리턴하는 함수 average3() 작성하기
# 해당 average3(2, 3, 4)를 테스트하여 결과가 3이 나오는지 확인

def average3(x, y, z):
  result = (x + y + z)/3
  return result
  
  average3(2, 3, 4)
  
# result
# 3.0
 
 
# 연습문제 3
# 1개의 리스트를 입력받아 리스트의 평균을 구하는 average() 함수를 작성
# average([2, 3, 4, 5, 6]) 을 테스트하여 결과가 4가 나오는지 확인

def average(nums):
  avg = sum(nums)/ len(nums)
  return avg
  
average([2, 3, 4, 5, 6,])

# result
# 4.0

# 연습문제 4
# 길이가 같은 두 개의 리스트를 입력받아 첫 번째 입력받은 리스트를 key, 두 번째 입력받은 리스트를 value로 하는 딕셔너리를 리턴하는 함수 to_dict()를 작성
# to_dict(['오즈', '레오', '선미'], ['고양이', '강아지', '인간'])의 결과가 {'오즈': '고양이', '레오': '강아지', '선미': '인간'}으로 나오는지 확인

# dic comprehension
def to_dict(k,v):
  return {i:j for  i,j in zip(k,v)}

to_dict(['오즈', '레오', '선미'], ['고양이', '강아지', '인간'])

# zip

def to_dict(name, species):
  d = {}
  for i,j in zip(name, species):
    d[i] = j
  return d

to_dict(['오즈', '레오', '선미'], ['고양이', '강아지', '인간'])

# range 활용
def to_dict(name, species):
  d = {}
  for i in range(len(name)):
    d[name[i]] = species[i]
  return d

to_dict(['오즈', '레오', '선미'], ['고양이', '강아지', '인간'])

# result
# {'오즈': '고양이', '레오': '강아지', '선미': '인간'}

```

<br>

### Lamda(익명함수)

- 일회성으로 함수 만들 때 사용

```python
def add(x,y):
  return x + y

add = lambda x, y: x + y

add(1,2)

# result
# 3
```

<br>

### Class

- 데이터와 함수를 같이 다루는 번들, 새로운 타입의 객체, 인스턴스를 만들 수 있음

```python
# class 만들기

class Cat:
  pass

# instance 만들기
# 클래스: 쿠키틀, 인스턴스: 쿠키
oz = Cat()
oreo = Cat()

# 조금 더 쓸모있는 class
class Cat:
  # Attribute: 클래스 안에 정의된 변수
  # class attribute
  home  = "sumi's house"

  # method 클래스 안에 정의된 함수 
  def set_name(self,name):
    # instance attribute
    self.name = name

oz = Cat()

oz.set_name('오즈')

oz.name

# result
# 오즈
```

<br>

### Attribute

- 클래스 안에 변수

```python
oz = Cat()
oreo = Cat()

print(oz.home) # 모든 인스턴스들이 가지고 있음
print(oreo.home)

# result
# sumi's house
# sumi's house

oz.set_name('오즈')
oreo.set_name('오레오')

# 두개의 인스턴스는 서로 영향을 받지 않음
print(oz.name)
print(oreo.name)

# result
# 오즈
# 오레오
```

<br>


### Method

- 클래스 안의 함수

```python
# Method
# 클래스안의 메서드

brand = 'datarian'

type(brand)

dir(oz)
```

<br>

### 클래스 연습문제

```python
# 연습문제 1
# 클래스 cat의 set_name 함수를 set_cat으로 수정하고 이름과 나이를 입력받도록 만들기

class Cat:

  def set_cat(self, name, age):
    self.name = name
    self.age = age
    return f'name: {self.name}, age:{self.age}'

my_cat = Cat()
my_cat.set_cat('oreo', 2)

# result
# name: oreo, age:2

# 연습문제 2
# 클래스 cat의 grow 메소드를 추가하여 실행될 때마다 고양이가 한살식 나이를 먹도록 

class Cat:

  def set_cat(self, name, age):
    self.name = name
    self.age = age
    return f'name: {self.name}, age:{self.age}'

  def grow(self):
    self.age += 1
    return f'current age: {self.age}'

my_cat = Cat()
my_cat.set_cat('bol',3)
my_cat.grow()

# result
# current age: 4
```

<br>

### 모듈과 패키지

```python
# 모듈과 패키지
# 모듈 불러오기

import math

math.sqrt(4)

# result
# 2.0
```

```python
# 패키지, 라이브러리 

from math import sqrt

sqrt(4)

# *로 import 지양, 필요라이브러리만 
from math import *

# 코랩은 이미 거의 다 설치되어 있음

# PyPI에 있는 패키지를 추출하여 자동으로 설치하는 pip 프로그램을 제공
# 설치할 때 pip install 패키지명

# result
# 2.0
```
