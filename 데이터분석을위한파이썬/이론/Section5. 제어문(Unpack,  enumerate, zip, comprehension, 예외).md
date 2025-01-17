### Section5. 제어문(Unpack, enumerate, zip, comprehension) 

<br>

## Unpacking 

- 데이터 구조에 담긴 값들을 여러 개의 변수로 나누기

```python
# 5-1. unpacking
# 데이터 구조에 담긴 값들을 여러 개의 변수로 나누기

t = (1, 2)
a, b = t

a

li = [1, 2]
c, d = li
```
<br>

```python
# for문과 함께 사용

hp = {'a1':100, 'a2': 200}

for i in hp.items(): 
  name, hp = i # for문 안에서 unpacking  가능 
  print(name)

# result 
# a1
# a2
```

<br>

- Unpacking시 변수의 개수 주의

```python
# unpacking 할때 변수의 갯수

pokemon = ['a1', 'a2', 'a3']

a,b = pokemon

# 변수의 갯수와 원소의 갯수가 일치하지 않아서 에러 발생 
```

<br>

- 일부를 제외하고 `Unpacking` 하기
    
    변수 담을 필요 없는 값이 있다면 언더바를 사용할 수 있음
    

```python
# 일부는 제외하고 unpacking 하기
pokemon = ['a1', 'a2', 'a3']

a, b, _ = pokemon

print(_)

# result
# a3
```

<br>

- Unpacking 남은 요소 전체를 변수에 할당

```python
pokemon = ['a1', 'a2', 'a3']

a, *b = pokemon

b

# a3
# ['a2', 'a3']
```

<br>

## Enumerate() 

- 인덱스를 붙여주는 역할을 함

```python
pokemon = ['a1', 'a2', 'a3']

list(enumerate(pokemon))

cnt = 0

for i in pokemon:
  print(cnt, i )
  cnt += 1

for idx, name in enumerate(pokemon):
  print(idx,name)
  
# result
# 0 a1
# 1 a2
# 2 a3
# 0 a1
# 1 a2
# 2 a3
```

<br>

## Zip()

- 같은 인덱스에 있는 위치들끼리 묶여짐

```python
fruit = ['apple', 'banana', 'melon']
sugar = [100, 50, 20]

list(zip(fruit, sugar))

# result
# [('apple', 100), ('banana', 50), ('melon', 20)]
```

<br>

- for문과 함께 사용

```python
sugar_list = {}

for n, h in zip(fruit, sugar):
  sugar_list[n] = h

sugar_list

# result
# {'apple': 100, 'banana': 50, 'melon': 20}
```

<br>

## Comprehension 

- list, dictionary 등 자료구조를 간단하게 만들 수 있는 파이썬의 독특한 문법

```python
sample = [1, 2, 3, 4, 5]

# 원소를 곱하기 2 하려면
double = []

for i in sample:
  double.append(i*2)

double
# result
# [2, 4, 6, 8, 10]

# List Comprehension
# sample 리스트 각각의 원소에 값을 1씩 더한 add_1 리스트 만들기

add_1 =  [i+1 for i in sample]
add_1

# result
# [2, 3, 4, 5, 6]
```

<br>

- 두 리스트 더하기

```python
x = [1, 2, 3, 4]
y = [10, 10, 20, 30]
add_2 = []

for a, b in zip(x,y):
  add_2.append(a + b)
  
# 결과
# [11, 12, 23, 34]

add_2 = [a + b for a,b in zip(x,y)]
add_2

# 결과
# [11, 12, 23, 34]
```
<br>

- 리스트 평평하게 만들기

```python
groups = [['apple', 'banana'], ['grape', 'melon']]

flat_list = []

for group in groups:
    for i in group:
      flat_list.append(i)

[i for group in groups for i in group]
flat_list

# result
# ['apple', 'banana', 'grape', 'melon']
```

<br>

- 데이터 필터링

```python
# 데이터 필터링

nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# 반복문 뒤에 있는 if는 필터링 되는 if문 
[i for i in nums if i % 2 == 0]

# result
# [2, 4, 6, 8, 10]
```

<br>

## Dict comprehension 📖

```python
fruit = ['apple', 'banana', 'melon']
sugar = [100, 50, 20]

favorit_fruit = {}

for f,s in zip(fruit, sugar):
  favorit_fruit[f] = s
  
# result
# {'apple': 100, 'banana': 50, 'melon': 20}

favorit_fruit = {n:h for n,h in zip(fruit, sugar)}

favorit_fruit

# result
# {'apple': 100, 'banana': 50, 'melon': 20}
```

<br>

### Key와 Value값 바꾸기

```python
# key와 value값 바꾸기
favorit_fruit = {}

for f, s in zip (fruit, sugar):
  favorit_fruit[s] = f

favorit_fruit

{s:f for s,f in zip(fruit,sugar)}

favorit_fruit

# result
# {100: 'apple', 50: 'banana', 20: 'melon'}
```

<br>

### 딕셔너리 데이터 필터링

```python
fruit = ['apple', 'banana', 'melon']
sugar = [100, 50, 20]

strong = {}

for f,s in favorit_fruit.items():
  if int(s) >= 100:
    strong[f] = s

strong

# result
# {'apple': 100}

strong = {n: h for n, h in favorit_fruit.items() if h >= 100}
strong

# result
# {'apple': 100}

```

<br>

## Try except 🔧

```python
# 5-4
# try except

try:
  print("실행을 시도합니다.")
except:
  print("에러가 발생하면 실행됩니다.")
  

# result
# 실행을 시도합니다.

```

<br>

### Try except를 사용해 에러를 예외처리

```python
#  try except를 사용해 에러를 예외처리
try:
  print("실행을 시도합니다.")
  x = 1 / 0
  print("실행에 성공했습니다.")
except:
  print("에러가 발생하면 실행됩니다.")
  
# result
# 실행을 시도합니다.
# 에러가 발생하면 실행됩니다.
```

<br>

### 특정 에러만 예외처리하기

```python
# 특정 에러만 예외처리
try:
  print("실행을 시도합니다.")
  x = 1 / 0
  print("실행에 성공했습니다.")
except ZeroDivisionError:
  x= 1E100
  print(x)

# result
# 1e+100
```

<br>

### 에러메세지 참조하기

```python
try:
  x = 1 / 0
except Exception as err:
  print(type(err),err)
  
# result
# <class 'ZeroDivisionError'> division by zero
```
