### Section3. 기본데이터구조 - 연습문제
<br>


####  파이썬 자료 구조와 함께 사용할 수 있는 내장 함수 소개
```python
>>> max([1, 2, 3]) # 최댓깂
3

>>> min([1, 2, 3]) # 최솟값
1

>>> sum([1, 2, 3]) # 합계
6

>>> len([1, 2, 3]) # 길이
3
```

<br>

#### 💡참고

* https://docs.python.org/ko/3/library/functions.html

<br>

#### 1. 아래 리스트에서 3번째 원소 파이리를 출력해보세요.

```python

pokemon = ['피카츄', '라이츄', '파이리', '꼬부기']

pokemon = ['피카츄', '라이츄', '파이리', '꼬부기']

pokemon[2]

```

<br>


#### 2. 슬라이싱을 이용해 위의 리스트 pokemon 의 1번째부터 3번째 원소까지 출력해보세요.

```python
pokemon[1:4]
```

<br>

#### 3. 아래 리스트를 순서대로 정렬해보세요.
```
a = [100, 5, 44, 20]
```

```python
a = [100, 5, 44, 20]
a.sort
a
```

<br>


#### 4. 리스트 a 의 가장 큰 값을 출력해보세요.
```python
max(a)
```

<br>

#### 5. 리스트 a 의 가장 작은 값을 출력해보세요.
```python
min(a)
```

<br>

#### 6. 아래 리스트의 평균을 구해보세요.
```python
sum(a)/len(a)
```

<br>


#### 7. 아래 리스트에 `'잉어킹'`을 요소로 추가해보세요.

```water_type_pokemon = ['꼬부기', '수륙챙이', '미뇽', '갸랴도스']```

```python
water_type_pokemon = ['꼬부기', '수륙챙이', '미뇽', '갸랴도스']
water_type_pokemon.append('잉어킹')
water_type_pokemon
```



#### 8. 아래 딕셔너리에서 `'꼬부기'`(key) 에 해당하는 값(value)을 출력해보세요.

```pokemon_evolution = {'피카츄':'라이츄', '꼬부기':'어니부기', '파이리':'리자드', '이상해씨':'이상해풀'}```


```python
pokemon_evolution = {'피카츄':'라이츄', '꼬부기':'어니부기', '파이리':'리자드', '이상해씨':'이상해풀'}
pokemon_evolution['꼬부기']
```

<br>

#### 9. 아래 리스트에서 중복을 제거해보세요.
```grass_type_pokemon = ['이상해씨', '이상해씨', '이상해풀', '이상해꽃', '이상해풀', '이상해씨']```

```python
grass_type_pokemon = ['이상해씨', '이상해씨', '이상해풀', '이상해꽃', '이상해풀', '이상해씨']

grass_type_pokemon = set(grass_type_pokemon)
grass_type_pokemon
```

<br>

#### 10. 아래 두 셋(set)에 있는 모든 요소를 합쳐서 출력해보세요.

```python
water_type_pokemon = {'꼬부기', '수륙챙이', '미뇽', '갸라도스'}
rock_type_pokemon = {'꼬마돌', '롱스톤'}
```
```python
water_type_pokemon = {'꼬부기', '수륙챙이', '미뇽', '갸라도스'}
rock_type_pokemon = {'꼬마돌', '롱스톤'}
water_type_pokemon | rock_type_pokemon
```
