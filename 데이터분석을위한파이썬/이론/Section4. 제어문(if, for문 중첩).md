

```python
# if
# 주어진 조건에 따라 다른 결과를 출력하고 싶을 때 사용

score = int(input('시험 점수를 입력해주세요: '))

if score >= 90:
  print("A학점 입니다.")
elif score >= 80:
  print("c학점 입니다.")
else:
  print("F학점 입니다.")

# 중첩 if문 사용, 학점 판별기

score = 90
assignment = True

if score >= 70:
  if assignment:
    print('A학점 입니다.')
  else:
    print('B학점 입니다.')
else:
  print('F학점 입니다.')

# for 반복문
# 반복적으로 작업을 실행할 때 사용

for i in [1, 2, 3, 4, 5]:
  print(i);

x = -1

if x < 0:
    print('음수')
elif x==0:
    print('0')
else:
    print('양수')

t = "aa cc dd"

for i in t:
  print(i)

# for과 list, tuple
my_list = ['aaa', 'bbb', 'ccc', 'ddd', 'eee']

for i in my_list:
  print(i)

# list에 원소 추가
nums = []

nums.append(1)

for i in range(10) :
  nums.append(i)

print(nums)

# for와 dictionary
my_dic = {"apple": "red", "banana": "yellow"}

for i in my_dic:
  print(i)

for i in my_dic.values():
  print(i)

for i in my_dic.items():
  print(i)

# 딕셔너리에 데이터 삽입
my_pokemon_hp = {}
my_pokemon = ["a1", "a2", "a3"]

for i in my_pokemon:
    my_pokemon_hp[i] = 100

my_pokemon_hp

# 특정 횟수만큼 반복되는 while 문

cnt = 0
while cnt < 2:
  print('피카')
  cnt += 1

# break, continue
# break를 사용해 for나 while 같은 반복문을 빠져 나올 수 있음

while True:
  answer = input('사계절 중 현재 날씨는?')
  if answer == '겨울':
    print('정답!')
    break
  else:
    print('땡! 다시 시도 하세요.');

for i in range(10):
  if i == 5:
    continue
  print(i)

```
