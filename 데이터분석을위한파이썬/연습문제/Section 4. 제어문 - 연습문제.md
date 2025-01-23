### Section4. 제어문 - 연습문제

### Q1. `for` 와 `range()`를 활용하여 1~10까지 수를 출력해보세요.

```python
for i in range(1,11):
  print(i)
```

<br>


### Q2. while 문을 이용하여 0에서 20까지 숫자를 출력해보세요.

```python
i=-1
while i < 20:
  i += 1
  print(i)
```

<br>

### Q3. `While` 을 사용해서 아래와 같은 모양을 만들어 보세요.

```
**********
*********
********
*******
******
*****
****
***
**
*
```

```python
cnt = 11

while cnt >= 1:
  cnt -= 1
  print("*" * cnt)
```
<br>


### Q4. 실수 x 값을 입력 받고, 입력 받은 숫자가 음수인지, 양수인지, 또는 0인지 확인하는 코드를 작성하세요.

```python
x = input('숫자를 입력해주세요 >> ')
x = int(x)

if x < 0:
  print('음수입니다.')
elif x > 0:
  print('양수입니다.')
else:
  print('0입니다.')
```

<br>

### Q5. for 문을 이용해 `my_list`의 평균을 구하세요.

```python
my_list = [10, 25, 78, 456]
sum = 0
length = 0

for i in  my_list:
  sum += i
  length += 1
avg = sum/length
print(avg)
```

<br>

### Q6. `if` 문을 활용해서 윤년 판별기를 만들어주세요.
```
1. 연수가 4로 나누어 떨어지는 해는 윤년으로한다. (ex. 2004년)
2. 연수가 100으로 나누어 떨어지는 해는 평년으로 한다. (ex. 1900년)
3. 연수가 400으로 나누어 떨어지는 해는 윤년이다. (ex. 2000년)
4. 이외에는 평년으로 한다.
```

```python
x = input('숫자를 입력해주세요.')
x = int(x)

if x % 4 == 0:
  if x % 100 == 0:
    if x % 400 == 0:
      print(x, '년도는 윤년입니다.')
    else:
      print(x, '년도는 평년입니다.')
  else:
    print(x, '년도는 윤년입니다.')
else:
  print(x, '년도는 평년입니다.')
```

<br>

###  Q7. 누군가 당신의 체육관에 결투 신청을 했습니다. 포켓몬의 체력이 100 이상 일 경우에만 다른 포켓몬과 결투를 할 수 있습니다.
### 당신의 포켓몬 중 결투에 내보낼 수 있는 포켓몬은 누구인가요? `for` 문과 `if` 을 사용해서 출력해주세요.

```python
my_pokemon_hp = {
    '피카츄': 100,
    '꼬북이': 90,
    '파이리': 80,
    '이상해씨': 140
}

for n, h in my_pokemon_hp.items():
  if h >= 100:
    print(n)
```

<br>

### Q8. 상대방 포켓몬과 결투를 하게 되었습니다.

* 내 포켓몬 수가 상대방 포켓몬 수 보다 많으면, 체력이 100이상인 포켓몬을 내보내고
* 내 포켓몬의 수가 상대방 포켓몬 수와 비교해 같거나 적으면 도망치고 싶습니다.

### 내 포켓몬 정보는 `my_pokemon_hp`에 있고, 상대방 포켓몬의 정보는 `opponent_pokemon` 에 있습니다.

### 도망쳐야 할까요? 싸워야 할까요? 싸운다면 어떤 포켓몬을 내보낼까요?

```python
cnt = 0
my_pokemon_hp = {
    '피카츄': 100,
    '꼬북이': 90,
    '파이리': 80,
    '이상해씨': 140
}

your_pokemon = ['냐옹이', '마자용']

for name, hp in my_pokemon_hp.items():

  if hp >= 100:
    if len(my_pokemon_hp) <= len(your_pokemon):
      continue
    else:
      print(name)
      del(name)
```

<br>


###  Q9.사용자가 입력한 2 ~ 9 사이의 정수를 입력받아 해당 정수의 구구단을 출력하세요. `if` 문과 `for` 문을 사용하세요.
### 만약 입력받은 값이 2~9 사이의 숫자가 아닐 경우 '잘못 입력하셨습니다.'를 대신 출력합니다.

```python
x = input('숫자를 입력해주세요: ')

x = int(x)

if (x >= 2) & (x <= 9):
  for i in range(1,10):
    print(x, '*', i, '= ', x*i)
else:
  print('잘못 입력하셨습니다.')
```

<br>

### Q10. `while` 문을 작성하여 0~50 사이의 숫자 중 7로 끝나는 숫자만 출력하게 만드세요.
```python
i = 0

while True:
    if i > 50:
        break
    if i % 10 == 7:
        print(i)
    i += 1
```
