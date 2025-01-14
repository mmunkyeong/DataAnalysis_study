## Pandas
- 다양한 데이터를 읽고 처리하는데 편리한 라이브러리
- Pandas를 이용해서 “.csv” 파일을 이용해서 분석하기 편리함
- 결측성 데이터(손실된 데이터)를 보정할 수 있고, 데이터의 추가, 삭제, 정렬과
조작 등이 가능함(전처리)
- Numpy는 행렬 데이터를 지원하나, 데이터를 분석하는데 있어 필요한 속성이지
만 행이나 열의 레이블이 없다. 하지만, Pandas는 이러한 문제를 해결할 수 있
음


- 리스트, 딕셔너리, 넘파이 배열을 데이터 프레임으로 변환
- ‘.csv’, ‘excel’, ‘JSON’ 등의 다양한 포맷의 파일을 처리
- 데이터의 결측치 처리를 위해서 데이터 보기, 검사, 필터, 정렬, 그룹화 및 정제


```python
pip intall pandas

import pandas as pd
```

<br>

### 1. Pandas: 시리즈와 데이터

- pandas의 데이터 구조는 numpy 배열을 이용하여 계산
- 인덱스(index)와 컬럼(columns)가 동일하게 적용
- Pandas는 시리즈(series) 클래스와 데이터프레임(data frame)클래스를 사용

<br>

### 2. Pandas: 데이터 프레임

- DataFrame(데이터 프레임)
    - 2차원의 데이터 구조로 index가 row와 column으로 구성
    - column들이 서로 다른 타입이어도 무방
    - row는 각 개별 테이터를 , column은 각 개별 속성을 나타냄
    - row및 column의 산술연산이 가능

```python
name_series = pd.Series(['alis', 'ves', 'hins','kay'])
age_series = pd.Series([30,25,21,30])
s_series = pd.Series(['여','여','남','남'])
math_grade_series = pd.Series(['A+','A0', 'A-','B+'])

frame = pd.DataFrame({'이름':name_series, '나이':age_series,\
                      '성별':s_series, '수학학점': math_grade_series})
```

<br>

- 예제

![image](https://github.com/user-attachments/assets/0674020b-b468-4173-a13d-b437cecb71b1)

<br>

### 3. Pandas: 데이터프레임 파일

- DataFrame(데이터 프레임)
- CSV, JSON, HTML을 데이터 프래임으로 변환할 수 있음
- 사용법
예) read_csv(filepath, sep, delimiter, header, names, index_col,encoding,......)
- filepath : 파일경로를 지정
- sep : 각데이터를 구별하기위한 구분자
- header: column의 이름과 sata시작을 나타낼 row인덱스 설정
- column의 이름으로 사용할 리스트 지정
- endoding:한글을 불러 올 경우 ‘utf-8’ or ‘CP949’ 를 설정

<br>

### 4. Pandas:데이터 전처리

- Dataframe에 새로운 데이터 입력
- dataframe[‘새로운 열 이름’] = ‘해당데이터 입력’
- df.describe()
    - count, mean, std, min, 25%, 50%, 75%, max 값을 표시
- df[:3]: 3개의 행 출력
- df.loc(‘index’)
    - row index의 값을 선택해서 Series형태로 보여줌
- df.iloc(‘index’)
    - row index의 default값을 선택해서 Series형태로 보여줌
- df.sort_values(‘col’)
    - row index의 default값을 선택해서 Series형태로 보여줌

<br>

- df.shape :데이터프레임 구조 파악
- df.columns : 데이터프레임 컬럼 특성 파악
- pd.concat(df1, df2,….)
- 두개의 데이터 프레임 합치기
    - [df.info](http://df.info/)() : 데이터 프레임의 정보를 파악하기
- df[‘col’].value_counts()
    - ‘col의 각기 다른 값의 개수를 계산하기
- df.fillna(value) : na값을 value 으로 채우기
- df.isnull().sum() : 각 행의 null 로 된 값의 개수를 세어준다.
- df.drop(): 행의 삭제

<br>

### 5. Pandas: Groupby

- groupby 연산은 기존 객체에 대해 다음의 연산을 함
- 데이터 분할하기
    - 객체를 분할할 때는 인자로 column이름이나 리스트 사용
    ->dataframe.groupby(‘column 인자’)
    - index를 통한 객체 분할 : dataframe.set_index(‘column 인자’)
- 데이터 연산하기
    - count(),sum(), min(), max(), mean(), std(), var(), describe()
    - pivot(), pivot_table() : 여러가지 분류로 섞인 DataFrame을 내가 원하는
    Index와 column으로 정렬
- 데이터 병합하기
    - concat() 함수를 이용하여 데이터 프레임을 병합
    - dataframe.concat(“list 이름”, axis = ‘0’ or ‘1’, join = ‘inner’ or
    ‘outer’)

<br>

```python
import pandas as pd
import numpy as np
 
data11 = pd.DataFrame( {'A' : ['a1','a2','a3'], 'B' : ['b1','b2','b3'], 'C' : ['c1','c2','c3']}, index = ['가','나','다'])
data2 = pd.DataFrame( {'B' : ['B1','B2','B3'], 'C' : ['C1','C2','C3'], 'D' : ['D1','D2','D3']}, index = ['다','라','마'])
 
data11
data2
```

![image](https://github.com/user-attachments/assets/e51562e5-1909-4ef9-9adf-5084686d0986)

<br>

## 시각화(matplotlib/Seaborn)

### 데이터 시각화 함수

- plt.rcParams : 라벨의 한글 깨지는 것을 방지하기 위한 설정
- plt.plot() : 선그리기
- plt.scatter() : 산포도 그리기
- plt.figure (figsize=(가로크기, 세로크기)) : 그림 크기 설정
- plt.grid() : 그리드로 화면 표시하기
- plt.subplots(figuresize=(가로크기,세로크기), ncols=세로개수, nrows =가
로개수, index=인덱스 개수) : 그림 크기와 개수 설정
- plt.show() : 최종 그림 그리기

<br>

### 시각화: Seaborn

- matplotlib 보다 조금 세련된 그래프를 디자인 할 수 있음.
- 최근의 시각화 라이브러리이기 때문에 pandas와 더 잘 호환되는 특징이 있음

```python
pip install seaborn

import seaborn as sns
```

<br>

- sns.scatterplot(x,y,data, hue , style) : seaborn 을 활용하여 산점도를 그리는 방법. x,y는 속성의 이름, data는 데이터 프레임,numpy 등, hue는 색깔별로 나타내는 그룹 속성 변수, style는 그룹화 속성을 모양별로 나타내는 변수
- sns.pairplot (df, hue=‘’……) : seaborn을 활용하여 변수(속성)와의 관계를 나타내는 시각화 방법
- sns.boxplot(df, x, y, hue,….) : 데이터 프레임, x와 y데이터를 주면 그에 따른 boxplot을 그리게 된다.
- sns.stripplot(df, x,y, hue,……) : 데이터 프레임과 x, y 데이속성을 지정하면, hue 설정을 하면 그에 따른 데이터의 점분포를 각각 hue의 특성에 맞게 그려준다.

```python
import seaborn as sns
import pandas as pd
from sklearn.datasets import load_iris

# Load the Iris dataset
iris = load_iris()
iris_df = pd.DataFrame(iris.data, columns=iris.feature_names)
iris_df['class'] = iris.target
iris_df['class'] = iris_df['class'].map({0: 'Setosa', 1: 'Versicolour', 2: 'Virginica'})

# Create a scatterplot
sns.scatterplot(x='sepal length (cm)', y='sepal width (cm)', data=iris_df, hue='class', style='class')
```


![image](https://github.com/user-attachments/assets/7f70f3d1-e69a-40fa-ad22-0ad5ab167b77)


<br>

```python
sns.pairplot(iris_df, hue='class')
```

![image](https://github.com/user-attachments/assets/5608a47e-cf75-4d44-b390-5c231f8fa638)
