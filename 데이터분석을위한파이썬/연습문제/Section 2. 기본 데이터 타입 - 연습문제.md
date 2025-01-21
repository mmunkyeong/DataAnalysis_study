
### Section 2. 기본 데이터 타입 - 연습문제

<br>

#### Q1.my_name이라는 변수에 본인의 이름을 저장하고, my_pokemon에 피카츄를 저장해 보세요. (저장하고 확인까지 해보세요.)

```python
my_name = 'munkyeong'
my_pockemon = '피카츄'
```

<br>

#### Q2. my_age라는 변수에 본인의 나이를, pokemon_age에 3을 숫자형으로 저장해 보세요.

```python
my_age = 26
pockemon_age = 3
```

<br>


#### Q3.my_height에 본인의 키를 소수자리까지 저장하고, pika_height에 피카츄의 키를 저장한 후, 각각의 type을 확인해 보세요.(단위 cm)


```python
my_height = 168.3
pika_height = 100

type(my_height)
type(pika_height)

```

<br>


#### Q4.나와 포켓몬의 나이 차이를 출력해 보세요. (my_age에서 pika_age를 뺀 값을 출력해 보세요.)

```python

my_age -= pockemon_age

my_age
```

<br>

#### Q5.'피카'를 10번 출력해 보세요.

```python
'피카'*10
```

<br>

#### Q6. 내 이름과 내 나이, 포켓몬 이름과, 피카츄 나이를 다음과 같은 형식으로 출력하는 코드를 써보세요.

```python
내 이름은 선미, 10살이지.
내 포켓몬은 피카츄, 3살이야.
```
```python 
print(f'내 이름은 {my_name}, {my_age}이지.')
print(f'내 포켓몬은 {my_pockemon}, {pockemon_age}이야.')
```

<br>

#### Q7.내 키가 피카츄보다 큰지 확인하는 코드를 작성해 보세요. 확인 값은 불리언 타입으로 출력하세요.

```python
my_height > pika_height
```

<br>

#### Q8. kobuk_age에 3살을 저장한 후, 피카츄와 나이가 같은지 확인하여 출력하는 코드를 작성해 보세요. 확인한 값은 불리언 타입으로 출력하세요.
```python
kobuk_age = 3

kobuk_age == pockemon_age
```
<br>

#### Q9. 다음은 포켓몬 노래의 가사 일부입니다. song의 공백을 포함한 문자 길이가 어떻게 되는지 출력해 보세요.

```python
song = '피카츄 라이츄 파이리 꼬북이 버터플 야도란 피존투 또가스 서로생긴 모습은 달라도 우리는 모두친구'
```

```python
len(song)
```

<br>


#### Q10. 위 노래 song을 띄어쓰기를 기준으로 words라는 변수명에 저장해 보세요.
- 힌트1 : string에서 사용할 수 있는 메서드들을 확인해 보세요.
- 힌트2 : split()을 사용해 보세요.

```python
words = song.split()

words
```
