### Section 5. 제어문(심화) - 연습문제

#### Q1. 리스트 컴프리헨션을 이용해서 1~10까지의  홀수를 구하세요.
```python
num = [i for i in range(1, 10) if i % 2 == 1]
print(num)
```

<br>

#### Q2.`enumerate` 내장 함수를 사용해서 my_fruits 리스트의 인덱스와 원소를 출력하세요.

```python
>>> number = [10, 20, 30]
>>> for i, number in enumerate(number):
>>> print(i, number)

0 10
1 20
2 30
```

```python
my_fruits = ['apple', 'banana', 'grape', 'lemon']

for i, f in enumerate(my_fruits):
  print(i, f)
```
<br>

#### Q3. `zip` 함수를 이용하여 fruit 리스트와 color 리스트를 묶고, 아래와 같은 **리스트**를 만들어주세요.

```python
[('apple', 'red'), ('banana', 'yellow'), ('orange', 'orange')]
```

```
fruit = ['apple', 'banana', 'orange']
color = ['red', 'yello', 'orange']

result = list(zip(fruit, color))
print(result)
```
<br>

#### Q4. `zip` 함수를 이용하여 fruit 리스트와 color 리스트를 묶고, dict 컴프리헨션을 이용하여 아래와 같은 **딕셔너리**를 만들어주세요.

```python
fruit = ['apple', 'banana', 'orange']
color = ['red', 'yello', 'orange']

result = {f:c for f,c in zip(fruit, color)}
print(result)
```

<br>

#### Q5.`dict 컴프리헨션`을 이용하여 아래와 같이 key, vaule 값을 바꿔 **딕셔너리**를 출력하세요.

```python
{'red': 'apple', : 'yello' : 'banana', 'orange': 'orange'}
```

💡참고

```python
>>> pokemon = ['피카츄', '꼬북이']
>>> hp = [100, 105]
>>> vaule_change = {h: n for n, h in zip(pokemon, hp)}
>>> print(vaule_change)

{100: '피카츄', 105: '꼬북이'}
```

```python
result = {c:f for c,f in zip(color, fruit)}
print(result)
```
<br>


#### Q6. `dict 컴프리헨션`을 이용하여 아래와 같이 key, vaule 값을 바꿔 **딕셔너리**를 출력하세요.

```python
{'red': 'apple', : 'yello' : 'banana', 'orange': 'orange'}
```
💡참고

```python
>>> pokemon = {'피카츄': 100, '꼬북이': 105}
>>> vaule_change = {h: n for n, h in pokemon.items()}
>>> print(vaule_change)

{100: '피카츄', 105: '꼬북이'}
```

```python
fruit_color = {'apple': 'red', 'banana': 'yello', 'orange': 'orange'}
# 답을 입력해주세요.
fruit_color = {'apple': 'red', 'banana': 'yello', 'orange': 'orange'}

value_change = {v:k for v,k in fruit_color.items()}
print(value_change)
```

#### Q7 `try`와 `except`을 이용하여 `1/0` 코드를 실행했을 때 발생하는 오류 메시지를 출력해주세요.

💡참고
```python
>>> try:
>>>     '1' + 0
>>> except TypeError as e:
>>>     print(f'에러메시지: {e}')

에러메시지: can only concatenate str (not "int") to str
```

```
try:
  1/0
except Exception as e:
  print(f'error message: {e}')
```
