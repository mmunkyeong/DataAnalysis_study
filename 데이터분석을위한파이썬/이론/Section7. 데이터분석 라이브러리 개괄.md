## Pandas

- 데이터 필터링, 테이블의 모양의 데이터를 다룸, 시각화, 전체 데이터 모양 확인, 탐색적 데이터 분석

```python
import pandas as pd

coord = pd.read_csv('https://raw.githubusercontent.com/datarian-kr/pandas/main/data/anscombes.csv')
```

<br>

```python
# 맨위에 있는 데이터 2개 

coord.head(2)

len(coord)

# result
# 44
```

![image (2)](https://github.com/user-attachments/assets/c68fb755-8e03-4467-ab80-f3353e3df752)

<br>

### 분포 그리기

```python
coord.plot.scatter(x='x', y='y', alpha = 0.5)
```
![image (3)](https://github.com/user-attachments/assets/952f419b-1f9a-43e7-9ec4-c44b087d7afd)

<br>


### 1. 각 데이터 셋의 평균과 표준편차 구하기

- dataset I의 x와 y의 평균과 표준편차

```python
coord.loc[coord['dataset'] == 'I',['x','y']].describe()
```
![image (4)](https://github.com/user-attachments/assets/b39e3a5c-38f1-4c38-8919-5cd9f16d3006)

<br>

- dataset II 의 x와 y의 평균과 표준편차

```python
coord.loc[coord['dataset'] == 'II',['x','y']].describe()
```
![image (5)](https://github.com/user-attachments/assets/ff37bad8-ddfa-42eb-88ce-0b6383d6a46c)

<br>


- dataset III의 x와 y의 평균과 표준편차

```python
coord.loc[coord['dataset'] == 'III',['x','y']].describe()
```
![image (6)](https://github.com/user-attachments/assets/3c9b7c6f-abe1-4249-b702-0aba5fbec014)

<br>

- dataset IV의 x와 y의 평균과 표준편차

```python
coord.loc[coord['dataset'] == 'IV',['x','y']].describe()
```
![image (7)](https://github.com/user-attachments/assets/facb677c-1b09-4dae-ad29-dd8d555f8ed3)


<br>

### 2. 각 데이터셋의 산포도 그리기

```python
# 질문: Dataset I ~ IV 들의 산포도가 비슷한가? 평균과 분산이 같은 데이터셋은 비슷한 분포를 가졌을 것이라고 가정할 수 있는가?
# 답변: Dataset I ~ IV x,y의 평균, 분산이 모두 비슷하지만 산포도는 다른 모양을 가짐. 이로써 평균과 분산이 같은 데이터셋이라도 완전히 다른 분포, 성질을 가질 수 있음 알 수 있다.

<br>

# Dataset I
coord[coord['dataset'] == 'I'].plot.scatter(x='x', y='y', alpha=0.5)
```
![image (8)](https://github.com/user-attachments/assets/4336c00f-d724-4df6-bc0a-29459fb21cf8)

<br>


```python
# Dataset II
coord[coord['dataset'] == 'II'].plot.scatter(x='x', y='y', alpha=0.5)
```
![image (9)](https://github.com/user-attachments/assets/9bb6a591-fb1b-409c-ac98-0177ae44f30d)

<br>



```python
# Dataset III
coord[coord['dataset'] == 'III'].plot.scatter(x='x', y='y', alpha=0.5)
```
![image (10)](https://github.com/user-attachments/assets/536f95d3-9ace-4f63-851e-ea312e77b604)

<br>

```python
# Dataset IV
coord[coord['dataset'] == 'IV'].plot.scatter(x='x', y='y', alpha=0.5)
```
![image (11)](https://github.com/user-attachments/assets/c0511734-57ca-4b05-867e-a789b797fb17)

<br>


### 3. 머신러닝: 사이킷런 Scikit-Learn

```python
# scikit-learn

import pandas as pd

# 시각화 라이브러리
import seaborn as sns
import matplotlib.pyplot as plt

# 머신러닝
from sklearn.ensemble import RandomForestClassifier # 트리 구조의 classifier
from sklearn.model_selection import train_test_split
#from sklearn.metrics import plot_confusion_matrix
from sklearn.metrics import ConfusionMatrixDisplay
from sklearn.metrics import confusion_matrix
```

<br>

```python
# 학습을 시키긴 위한 데이터
train = pd.read_csv('https://raw.githubusercontent.com/datarian-kr/pandas/main/data/digit-recognizer/train.csv')

test = pd.read_csv('https://raw.githubusercontent.com/datarian-kr/pandas/main/data/digit-recognizer/test.csv')
```

<br>

```python
idx = 3
plt.imshow(train.iloc[idx,1:].values.reshape(28,28), cmap='gray')
plt.title(f'label: {train.iloc[idx,0]}')
```
![image (12)](https://github.com/user-attachments/assets/24ef3090-cfc7-4397-a119-68f724234e77)

<br>


```python
# train 데이터는 정답이 있음

train
```
![image (13)](https://github.com/user-attachments/assets/91bb232d-79f5-441f-9d68-550c0b19ecd8)


<br>

### 탐색적 데이터 분석

```python
# 탐색적 데이터 분석
# 라벨의 데이터가 0부터 9까지 있음

train['label'].hist()
```
<br>

### 3. 머신러닝: 사이킷런 Scikit-Learn(모델 만들고 평가하고 예측하기)

```python
# 모델 만들기
X_train = train.iloc[:,1:]
Y_train = train.iloc[:,0]
X_test = test
```

<br>

```python
# 정답이 있는 트레이닝 셋을 두개로 쪼갬 
train_image, vali_image, train_labels, vali_labels = train_test_split(X_train.copy(), Y_train.copy(), train_size = 0.8, random_state=42)
```

<br>

```python
forest = RandomForestClassifier(n_estimators=100, random_state=42)
forest.fit(train_image, train_labels)
```
![image (14)](https://github.com/user-attachments/assets/f9adfb4c-7e51-402b-aa73-f524d9c18cd4)


<br>


### 모델 평가

```python
# 모델 평가

# 남겨놓은 이미지 데이터를 넣고 예측을 해보기 
# 이미지도 있고 정답도 있기 때문에 모델이 예측한 값으로 비교해보기
# vali_pred : 예측된 값, vali_labels: 실제 값 -> 두가지를 비교 
vali_pred = forest.predict(vali_image)
```

<br>

```python
# true label 과 predict label이 일치하는 대각선 라인은 모델이 잘 예측한 부분, 노란색 부분은 실수한 부분

fig, ax = plt.subplots(figsize=(12,8))
ax = sns.heatmap(confusion_matrix(vali_labels, vali_pred), cmap = 'YlGnBu', annot=True, fmt='d')
ax.set(xlabel = 'Predicted Label', ylabel='True Label')
```
![image (15)](https://github.com/user-attachments/assets/11bbe76c-85de-4fe9-b68c-0b8955ecb1dd)

<br>


```python
# 모델은 어디서 실수 했는지 확인
# True Label이 4, predict Label 9 / 16개 데이터, 왜 9인지 확인

vali_all = vali_image.copy()
```

<br>

```python
vali_all.loc[:,'labels'] = vali_labels
vali_all.loc[:,'pred'] = vali_pred
```

<br>

```python
true_4 = vali_all['labels'] == 4
pred_9 = vali_all['pred'] == 9

sample = vali_all[true_4 & pred_9].copy()
```
![image (16)](https://github.com/user-attachments/assets/90aa91be-1adf-4c16-a345-2ad2ce0507c3)

<br>

```python
sample.index
```
![image (20)](https://github.com/user-attachments/assets/7649e7be-e987-4507-8fa2-6e1b30f66e84)

<br>


```python
# 실제로는 4인데 9로 예측된 샘플 

# 4인데 9로 볼 수 있기 때문에 -> 실수 데이터
idx = 26182

plt.imshow(vali_image.loc[idx, :].values.reshape(28,28), cmap = 'gray')
```

![image (17)](https://github.com/user-attachments/assets/0a762183-e287-47ca-8285-69b4a052ccdb)

<br>

### 예측

```python
# 예측

pred = forest.predict(X_test)

X_test['pred'] = pred
```

<br>

```python
X_test
```

![image (18)](https://github.com/user-attachments/assets/877814c3-09d3-4cad-9daf-4f797ae60e20)


<br>

```python
#  이미지 데이터 모델이 예측한 값은 9
idx = 3
print(X_test.iloc[idx, -1])
plt.imshow(X_test.iloc[idx,:-1].values.reshape(28,28), cmap='gray')
```
![image (19)](https://github.com/user-attachments/assets/0402aa1f-3a58-45da-a29f-5555ae9571e9)
