### **Python 기본 데이터 타입**

### **1. 숫자 Numbers**

숫자는 말 그대로 숫자 형태로 이루어진 데이터 타입입니다.

크게 정수형 int 와 실수형 float

<br>

### **2. 문자 Strings**

문자는 문자로 이루어진 데이터 타입입니다.

큰 따옴표나 작은 따옴표로 감싸 표현

<br>

### **3. 불리언 Boolean**

불리언은 `True` `False` 두 가지 값을 가지는 데이터 타입입니다.

True 는 1, False 는 0 으로도 표현

<br>

### **4. None**

파이썬에는 None 이라는 데이터 타입이 있습니다.

None 은 값이 없음을 뜻합니다.

숫자 `0` 과는 다른 값이고, Boolean 의 `False` 값과도 다릅니다

<br>

### **5. 형변환, Casting**

데이터 타입을 바꾸어줄 수 있습니다.

예를 들어, 숫자 데이터 타입을 `str( )` 안에 넣어주면 문자 데이터 타입이 됩니다.

<br>

## **문자열 String**

큰 따옴표를 3번 `"""..."""` 혹은 작은 따옴표를 3번 `'''...'''` 반복해서 사용함으로써 여러줄의 문자열

<br>

### **1. 문자열 합치기, 반복하기**

---

연산자를 사용해 문자열을 합치거나 반복할 수 있습니다.

`+` 연산자로 문자열끼리 합치고 , `*` 연산자를 사용해 문자열을 여러번 반복할 수 있음

<br>

### **2. 문자열 인덱싱 Indexing**

```python
car_brands = ['volvo', 'kia']
car_brands[0]
```

<br>

### **3. 문자열 슬라이싱 Slicing**

```python
# pokemon[n:m] # 인덱스 n ~ 인덱스 m-1
pokemon[0:2] # 0~1
```

<br>

### **4. 문자열의 길이 확인하기**

파이썬 내장함수 `len( )` 을 사용하여 문자열의 길이를 구할 수 있음

```python
len(pokemon)
```
<br>

## **문자열에서 사용할 수 있는 함수**

### **1. 문자열 내에서 특정 문자의 위치 찾기 find**

`find( )` 메소드를 사용해 문자열에서 특정 문자가 어디에 위치해있는지 확인할 수 있음

```python
pokemon
idx = pokemon.find('피')

idx
pokemon[idx]
```

<br>

### **2. 문자열 중 일부 대치하기 replace**

`replace( )` 메소드를 사용해서 문자열에 포함된 일부를 다른 내용으로 대치할 수

```python
pokemon = 피카츄
pokemon_1 = pokemon.replace('피카', '라이')
pokemon_1
#라이츄
```

<br>

### **3. 특정 문자로 문자열 나누기 split**

`split( )` 메소드를 사용해 문자열을 특정 문자로 나눌 수 있습니다.

괄호 안에 들어간 문자를 기준으로 문자열을 나누어 리스트로 반환

```python
sample = '피카츄 라이츄 파이리 꼬부기'
sample_splited = sample.split()

```

<br>

### **4. 문자열의 앞 뒤 공백 제거 strip**

`strip()` 메소드를 사용해 문자열의 앞, 뒤 공백을 제거

```python
pokemon = '    피카츄  '
pokemon = pokemon.strip()
pokemon
```

<br>


### **5. 대소문자 변환 upper, lower**

알파벳으로 이루어진 문자열을 사용할 때 대문자, 소문자로 변환

```python
sample = 'Pokemon'

sample_upper = sample.upper()
```

<br>

### `f-string` 에 변수 넣어주기

중괄호 `{ }` 를 사용해서 `f-string` 안에 원하는 값을 넣어줄 수

```python
x = 2
y = 2

f"{x} 더하기 {y}는 {x + y} 입니다."
```

```python
name = '데이터리안'

f'제 이름은 {name}입니다.'
```
