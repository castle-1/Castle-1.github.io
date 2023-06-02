---
layout: single
title:  "ch2_1 데이터 집합 불러오기(Import a data set)"
categories : pandas
---
# 데이터 집합 불러오기

### 데이터 분석의 시작은 데이터 불러오기부터

- 데이터 분석을 위해 가장 먼저 해야 할 일은 무엇일까?
- 데이터를 불러오는것!
- 이때 불러오는 데이터를 `데이터 집합` 이라고 한다.

##### gapminder 데이터 불러오기
- 판댜스의 여러가지 기능을 사용하려면 판다스 라이브러리를 불러와야한다.


```python
#판다스 라이브러리 불러오기
import pandas
```

- gapminder 에디터 집합을 불러오려면 `read_csv()` 메소드를 사용해야 한다.
- read_csv 메소는 `(,)쉼표`로 열이 구분되어 있는 데이터를 불러온다.
- gapminder은 `탭(tab)`으로 구분되어 있기 때문에 read_csv()를 호출할때 열이 탭으로 구분되어 있다고 알려줘야한다.
- `sep 속성값으로 '/t'`를 지정


```python
df = pandas.read_csv('data/gapminder.tsv', sep='\t')
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
      <th>lifeExp</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
      <td>28.801</td>
      <td>8425333</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1957</td>
      <td>30.332</td>
      <td>9240934</td>
      <td>820.853030</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1962</td>
      <td>31.997</td>
      <td>10267083</td>
      <td>853.100710</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1967</td>
      <td>34.020</td>
      <td>11537966</td>
      <td>836.197138</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1972</td>
      <td>36.088</td>
      <td>13079460</td>
      <td>739.981106</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1699</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1987</td>
      <td>62.351</td>
      <td>9216418</td>
      <td>706.157306</td>
    </tr>
    <tr>
      <th>1700</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1992</td>
      <td>60.377</td>
      <td>10704340</td>
      <td>693.420786</td>
    </tr>
    <tr>
      <th>1701</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1997</td>
      <td>46.809</td>
      <td>11404948</td>
      <td>792.449960</td>
    </tr>
    <tr>
      <th>1702</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2002</td>
      <td>39.989</td>
      <td>11926563</td>
      <td>672.038623</td>
    </tr>
    <tr>
      <th>1703</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2007</td>
      <td>43.487</td>
      <td>12311143</td>
      <td>469.709298</td>
    </tr>
  </tbody>
</table>
<p>1704 rows × 6 columns</p>
</div>



- 판다스에 있는 메소드를 호출하려면 `pandas`와 `점(.)` 연산자를 사용해야한다.
- 관습적으로 pandas를 pd로 줄여 사용


```python
import pandas as pd
df = pd.read_csv('data/gapminder.tsv', sep='\t')
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
      <th>lifeExp</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
      <td>28.801</td>
      <td>8425333</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1957</td>
      <td>30.332</td>
      <td>9240934</td>
      <td>820.853030</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1962</td>
      <td>31.997</td>
      <td>10267083</td>
      <td>853.100710</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1967</td>
      <td>34.020</td>
      <td>11537966</td>
      <td>836.197138</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1972</td>
      <td>36.088</td>
      <td>13079460</td>
      <td>739.981106</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1699</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1987</td>
      <td>62.351</td>
      <td>9216418</td>
      <td>706.157306</td>
    </tr>
    <tr>
      <th>1700</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1992</td>
      <td>60.377</td>
      <td>10704340</td>
      <td>693.420786</td>
    </tr>
    <tr>
      <th>1701</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1997</td>
      <td>46.809</td>
      <td>11404948</td>
      <td>792.449960</td>
    </tr>
    <tr>
      <th>1702</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2002</td>
      <td>39.989</td>
      <td>11926563</td>
      <td>672.038623</td>
    </tr>
    <tr>
      <th>1703</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2007</td>
      <td>43.487</td>
      <td>12311143</td>
      <td>469.709298</td>
    </tr>
  </tbody>
</table>
<p>1704 rows × 6 columns</p>
</div>



##### 시리즈와 데이터프레임

- 판다스는 데이터를 효율적으로 다루기 위해 `시리즈(series)`와 `데이터프레임(dataframe)`이라는 자료형을 사용한다.
- `데이터프레임`은 엑셀에서 `시트`와 동일한 개념이며 `시리즈`는 `시트의 열 1개`를 의미한다.
- 파이썬에 비유하면 데이터프레임은 시리즈들이 각 요소가되는 `딕셔너리`라고 생각하면 된다.

##### 불러온 데이터 집합 살펴보기(gapminder)

- `read_csv 메소드`는 데이터 집합을 읽어 들여와 데이터프레임이라는 자료형으로 반환한다.
- 데이터프레임에는 데이터 분석에 유용한 여러 메소드가 미리 정의되어 있다.
- `head()`메소드는 데이터프레임에서 가장 앞에 있는5개의 행을 출력하여 내가 불러온 데이터가 어떤 값을 가지고 있는지 살펴보기 안성맞춤이다.


```python
df.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
      <th>lifeExp</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
      <td>28.801</td>
      <td>8425333</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1957</td>
      <td>30.332</td>
      <td>9240934</td>
      <td>820.853030</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1962</td>
      <td>31.997</td>
      <td>10267083</td>
      <td>853.100710</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1967</td>
      <td>34.020</td>
      <td>11537966</td>
      <td>836.197138</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1972</td>
      <td>36.088</td>
      <td>13079460</td>
      <td>739.981106</td>
    </tr>
  </tbody>
</table>
</div>



##### type
- `type()`메소드는 자료형을 출력해준다.


```python
type(df)
```




    pandas.core.frame.DataFrame



##### shape 
- `shape`속성에는 데이터프레임 자신이 가지고 있는 데이터의 행과 열의 크기에 대한 정보를 저장하여 가지고 있다.
- 1번 째 값은 행의 크기
- 2번 째 값은 열의 크기


```python
df.shape
```




    (1704, 6)



##### gapminder 살펴보기
- `columns 속성`을 사용하면 데이터프레임의 열 이름을 확인할 수 있다.


```python
df.columns
```




    Index(['country', 'continent', 'year', 'lifeExp', 'pop', 'gdpPercap'], dtype='object')



##### info
- 데이터프레임을 구성하는 값의 자료형은 데이터프레임의 `dtypes 속성`이나 `info 메소드`로 쉽게 확인할 수 있다.


```python
print(df.dtypes,'\n')
print(df.info())
```

    country       object
    continent     object
    year           int64
    lifeExp      float64
    pop            int64
    gdpPercap    float64
    dtype: object 
    
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1704 entries, 0 to 1703
    Data columns (total 6 columns):
     #   Column     Non-Null Count  Dtype  
    ---  ------     --------------  -----  
     0   country    1704 non-null   object 
     1   continent  1704 non-null   object 
     2   year       1704 non-null   int64  
     3   lifeExp    1704 non-null   float64
     4   pop        1704 non-null   int64  
     5   gdpPercap  1704 non-null   float64
    dtypes: float64(2), int64(2), object(2)
    memory usage: 80.0+ KB
    None


##### 판다스와 파이썬 자료형 비교
- 판다스와 파이썬은 같은 자료형도 다르게 인식한다.
- ex)판다스는 문자열자료형을 `object`로 인식하고 파이썬은 `string`으로 인식한다.
<br>

|판다스 자료형|파이썬 자료형|설명|
|:---:|:---:|:---:|
|object|string|문자열|
|int64|int|정수|
|float64|float|소수점을 가진 숫자|
|datetime64|datetime|파이썬 표준 라이브러리인 datetime이 반환하는 자료형|

### 데이터 추출하기

#### 열 단위 데이터 추출하기
- 데이터를 열 단위로 추출하려면 `대괄호`와 `열 이름`을 사용해야 한다.
- 열 이름은 꼭 `작은따옴표`를 사용해서 지정해야한다.
- 추출한 열은 변수에 저장해서 사용할 수 있다.
- 1개의 열만 추출하면 시리즈를 얻을 수 있고 2개이상의 열을 추출하면 데이터프레임을 얻을 수 있다.

##### gapminder 데이터 사용해서 열단위로 데이터 추출하기
- ex) 데이터프레임에서 counrty인 열을 추출하여 country_df에 저장하기


```python
country_df = df['country']
print(country_df)
```

    0       Afghanistan
    1       Afghanistan
    2       Afghanistan
    3       Afghanistan
    4       Afghanistan
               ...     
    1699       Zimbabwe
    1700       Zimbabwe
    1701       Zimbabwe
    1702       Zimbabwe
    1703       Zimbabwe
    Name: country, Length: 1704, dtype: object


- type 메소드를 사용하면 country_df에 저장된 데이터의 자료형이 시리즈 라는것을 확인할 수 있다.


```python
type(country_df)
```




    pandas.core.series.Series



- 시리즈도 `head`, `tail` 매소드를 가지고 있다.


```python
print(country_df.head,'\n')
print(country_df.tail)
```

    <bound method NDFrame.head of 0       Afghanistan
    1       Afghanistan
    2       Afghanistan
    3       Afghanistan
    4       Afghanistan
               ...     
    1699       Zimbabwe
    1700       Zimbabwe
    1701       Zimbabwe
    1702       Zimbabwe
    1703       Zimbabwe
    Name: country, Length: 1704, dtype: object> 
    
    <bound method NDFrame.tail of 0       Afghanistan
    1       Afghanistan
    2       Afghanistan
    3       Afghanistan
    4       Afghanistan
               ...     
    1699       Zimbabwe
    1700       Zimbabwe
    1701       Zimbabwe
    1702       Zimbabwe
    1703       Zimbabwe
    Name: country, Length: 1704, dtype: object>


##### 리스트 열에 이름 전달하기
- `리스트` 열에 이름을 전달하면 여러 개의 열을 한 번에 추출할 수 있다.
- 1개의 열이 아니라 2개 이상의 열을 추출했기 때문에 시리즈가 아니라 데이터프레임을 얻을 수 있다.
- ex) 이름이 counrty, continent, year인 열을 subset에 저장


```python
subset = df[['country','continent','year']]
subset
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1957</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1962</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1967</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1972</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1699</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1987</td>
    </tr>
    <tr>
      <th>1700</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1992</td>
    </tr>
    <tr>
      <th>1701</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1997</td>
    </tr>
    <tr>
      <th>1702</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2002</td>
    </tr>
    <tr>
      <th>1703</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2007</td>
    </tr>
  </tbody>
</table>
<p>1704 rows × 3 columns</p>
</div>




```python
type(subset)
```




    pandas.core.frame.DataFrame



### 행단위 데이터 추출하기
- 데이터를 행단위로 추룰하려면 `loc`,`iloc`속성을 사용한다.
- loc : 인덱스를 기준으로 행 데이터 추출
- iloc : 핸 번호룰 기준으로 행 데이터 추출
- 파이썬에서는 리스트 같은 자료형에 저장된 데이터의 순서를 인덱스라고 한다.
- 판다스에서는 이런 개념을 행 번호라고 부른다.

### 인덱스와 행 번호 개념 알아보기
- 인덱스는 보통 0부터 시작하지만 행 데이터가 추가, 삭제 되면 언제든지 변할 수 있으며 숫자가 아니라 문자열을 사용할 수도있다.
- 행 번호는 데이터의 순서를 따라가기 때문에 정수만으로 데이터를 조회하거나 추출할 수있으며 실제 데이터프레임에서는 확인할 수 없는 값이다.

##### loc속성을 사영해서 gapminder 행 데이터 추출하기
- `loc 속성`에 대괄호를 이용하여 인덱스를 전달하면 행 데이터를 추출할 수 있다.
- -1과 같이 인덱스에 없는 값을 사용하면 오류가 발생
- ex) 인덱스가 0인 행 데이터 추출


```python
df.loc[0]
```




    country      Afghanistan
    continent           Asia
    year                1952
    lifeExp           28.801
    pop              8425333
    gdpPercap     779.445314
    Name: 0, dtype: object



##### 데이터프레임의 마지막 행 데이터를 추출
- 마지막행의 데이터 인덱스를 알아내야한다.
- shape[0]에 행크기가 저장되어 있다는 점을 이용하여 인덱스를 구하면 된다.
- ex) shape[0]에서 1을 뺀 값으로 마지막 행 데이터를 추출


```python
num_of_rows = df.shape[0]
last_of_index = num_of_rows - 1
df.loc[last_of_index]
```




    country        Zimbabwe
    continent        Africa
    year               2007
    lifeExp          43.487
    pop            12311143
    gdpPercap    469.709298
    Name: 1703, dtype: object



##### tail 메소드를 이용하여 마지막 행 데이터 추출
- `tail`매소드의 인자 n에 1을 전달하면 마지막 행의 데이터를 추출할 수 있다.


```python
df.tail(n=1)
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
      <th>lifeExp</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1703</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2007</td>
      <td>43.487</td>
      <td>12311143</td>
      <td>469.709298</td>
    </tr>
  </tbody>
</table>
</div>



##### 인덱스가 0, 9, 99 인 데이터 한 번에 추출하기
- 리스트에 원하는 인덱스를 담아 loc 속성에 절달하면 된다.


```python
df.loc[[0,9,99]]
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
      <th>lifeExp</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
      <td>28.801</td>
      <td>8425333</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1997</td>
      <td>41.763</td>
      <td>22227415</td>
      <td>635.341351</td>
    </tr>
    <tr>
      <th>99</th>
      <td>Bangladesh</td>
      <td>Asia</td>
      <td>1967</td>
      <td>43.453</td>
      <td>62821884</td>
      <td>721.186086</td>
    </tr>
  </tbody>
</table>
</div>



### tail메소드와 loc속성이 반환하는 자료형은 서로 다르다
- loc 속성이 반환한 데이터 자료형은 시리즈
- tail 메소드가 반환한 데이터 자료형은 데이터프레임


```python
subset_loc = df.loc[0]
subset_tail = df.tail(n=1)

print(type(subset_loc))
print(type(subset_tail))
```

    <class 'pandas.core.series.Series'>
    <class 'pandas.core.frame.DataFrame'>


### iloc 속성으로 행 데이터 추출하기
- loc 속성은 데이터프레임의 `인덱스`를 사용하여 데이터를 추출했지만 iloc 속성은 `데이터 순서를 의미하는 행 번호`를 사용하여 데이터를 추출한다.
- ex) iloc 속성에 1을 전달하여 데이터 추출


```python
df.iloc[1]
```




    country      Afghanistan
    continent           Asia
    year                1957
    lifeExp           30.332
    pop              9240934
    gdpPercap      820.85303
    Name: 1, dtype: object



##### iloc 속성은 음수를 사용해도 데이터 추출가능
- 데이터프레임에 아예 존재하지 않는 행 번호를 전달하면 오류발생
- ex) -1을 전달하여 `마지막 행` 데이터를 추출


```python
df.iloc[-1]
```




    country        Zimbabwe
    continent        Africa
    year               2007
    lifeExp          43.487
    pop            12311143
    gdpPercap    469.709298
    Name: 1703, dtype: object



##### iloc 속성도 여러 데이터를 한 번에 추출 가능
- 원하는 행 데이터의 행 번호를 `리스트`에 담아 전달


```python
df.iloc[[0,99,999]]
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
      <th>lifeExp</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
      <td>28.801</td>
      <td>8425333</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>99</th>
      <td>Bangladesh</td>
      <td>Asia</td>
      <td>1967</td>
      <td>43.453</td>
      <td>62821884</td>
      <td>721.186086</td>
    </tr>
    <tr>
      <th>999</th>
      <td>Mongolia</td>
      <td>Asia</td>
      <td>1967</td>
      <td>51.253</td>
      <td>1149500</td>
      <td>1226.041130</td>
    </tr>
  </tbody>
</table>
</div>



### loc, iloc속성 자유자재로 사용하기
- 두 속성 모두 추출할 데이터의 행을 먼저 지정하고 그런 다음 열을 지정하는 방법으로 데이터를 추출한다.
- ex) df.loc[[행],[열]] 이나 df.iloc[[행],[열]]
- 행과 열을 지정하는 방법은 `슬라이싱 구문`, `range 메소드`를 사용하는 방법이 있다.

### 슬라이싱 기법, range 메소드를 사용하여 데이터 추출하기

##### 슬라이싱 기법
- 모든 행(:)의 데이터에 대해 year,pop 열을 추출하는 방법
- lic와 iloc 속성에 전달하는 열 지정값은 반드시 형식에 맞게 전달해야한다.
- ex) loc 속성의 열 지정값에 정수 리스트를 전달하면 오류가 발생


```python
subset = df.loc[:,['year','pop']]
subset.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>pop</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1952</td>
      <td>8425333</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1957</td>
      <td>9240934</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1962</td>
      <td>10267083</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1967</td>
      <td>11537966</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1972</td>
      <td>13079460</td>
    </tr>
  </tbody>
</table>
</div>




```python
subset = df.iloc[:,[2,4,-1]] # 모든 행에대해서 2번 열,4번 열, -1(가장 마지막 열)
subset.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1952</td>
      <td>8425333</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1957</td>
      <td>9240934</td>
      <td>820.853030</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1962</td>
      <td>10267083</td>
      <td>853.100710</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1967</td>
      <td>11537966</td>
      <td>836.197138</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1972</td>
      <td>13079460</td>
      <td>739.981106</td>
    </tr>
  </tbody>
</table>
</div>



### range 메소드로 데이터 추출
- `range 메소드`는 지정한 구간의 정수 `리스트`를 반환해준다.
- iloc 속성의 `열 지정값에는 정수 리스트`를 전달해야 한다는 검과 `range 메소드의 반환값이 정수 리스트`인 점을 이용하여 원하는 데이터를 추출
- range 메소드는 지정한 범위의 `정수 리스트를 반환`하는것이 아니라 `제네레이터를 반환`
- iloc속성은 `제네레이터로 데이터 추출을 할 수 없다.`
- 제네레이터는 간단하게 `리스트로 변환할 수 있다.`


```python
small_range = list(range(5))
print(small_range)
print(type(small_range))
```

    [0, 1, 2, 3, 4]
    <class 'list'>



```python
subset = df.iloc[:,small_range]
subset.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
      <th>lifeExp</th>
      <th>pop</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
      <td>28.801</td>
      <td>8425333</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1957</td>
      <td>30.332</td>
      <td>9240934</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1962</td>
      <td>31.997</td>
      <td>10267083</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1967</td>
      <td>34.020</td>
      <td>11537966</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1972</td>
      <td>36.088</td>
      <td>13079460</td>
    </tr>
  </tbody>
</table>
</div>




```python
small_range = list(range(3,6))
small_range
```




    [3, 4, 5]




```python
subset = df.iloc[:,small_range]
subset.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>lifeExp</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>28.801</td>
      <td>8425333</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>1</th>
      <td>30.332</td>
      <td>9240934</td>
      <td>820.853030</td>
    </tr>
    <tr>
      <th>2</th>
      <td>31.997</td>
      <td>10267083</td>
      <td>853.100710</td>
    </tr>
    <tr>
      <th>3</th>
      <td>34.020</td>
      <td>11537966</td>
      <td>836.197138</td>
    </tr>
    <tr>
      <th>4</th>
      <td>36.088</td>
      <td>13079460</td>
      <td>739.981106</td>
    </tr>
  </tbody>
</table>
</div>



#####  ex) range(0,6,2)
- 0~5까지 2만큼 건너뛰는 제네레이터를 생성
- 리스트로 변환하면 범위는 0~5이고 짝수로 된 정수 리스트


```python
small_range = list(range(0,6,2))
subset = df.iloc[:,small_range]
subset.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>year</th>
      <th>pop</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>1952</td>
      <td>8425333</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>1957</td>
      <td>9240934</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>1962</td>
      <td>10267083</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>1967</td>
      <td>11537966</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>1972</td>
      <td>13079460</td>
    </tr>
  </tbody>
</table>
</div>



##### 슬라이싱과 range메소드 비교
- 실무에서는 range메소드 보다 슬라이싱을 선호
- range 메소드는 반환한 제네레이터를 리스트로 변환하는 등의 과정을 거치기 때문이다.
- ex) list(range(3))과 [:3]은 같은결과


```python
subset = df.iloc[:,:3]
subset.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>continent</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1957</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1962</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1967</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1972</td>
    </tr>
  </tbody>
</table>
</div>



##### 0:6:2를 열 지정값에 전달
- range(0,6,2)와 같은 결과


```python
subset = df.iloc[:,0:6:2]
subset.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>year</th>
      <th>pop</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>1952</td>
      <td>8425333</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>1957</td>
      <td>9240934</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>1962</td>
      <td>10267083</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>1967</td>
      <td>11537966</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>1972</td>
      <td>13079460</td>
    </tr>
  </tbody>
</table>
</div>



##### loc, iloc속성 자유자재로 사용하기
- ex) iloc속성으로 0,99,999 번째 행의 0,3,5번째 열 데이터를 추출하려면?


```python
subset = df.iloc[[0,99,999],[0,3,5]]
subset.head()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>lifeExp</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>28.801</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>99</th>
      <td>Bangladesh</td>
      <td>43.453</td>
      <td>721.186086</td>
    </tr>
    <tr>
      <th>999</th>
      <td>Mongolia</td>
      <td>51.253</td>
      <td>1226.041130</td>
    </tr>
  </tbody>
</table>
</div>



##### 주의
- iloc 속성의 열 지정값으로 정수 리스트를 전달하는 것이 간편해 보일 수 있지만 이렇게 작성한 코드는 나중에 어떤 데이터를 추출하기 위한 코드인지 파악하지 못 할 수도있다.
- 보통 loc 속성을 이용하여 열 지정값으로 열 이름을 전달한다.


```python
df.loc[[0,99,999],['country','lifeExp','gdpPercap']]
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>lifeExp</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>28.801</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>99</th>
      <td>Bangladesh</td>
      <td>43.453</td>
      <td>721.186086</td>
    </tr>
    <tr>
      <th>999</th>
      <td>Mongolia</td>
      <td>51.253</td>
      <td>1226.041130</td>
    </tr>
  </tbody>
</table>
</div>



### 연습문제
- 인덱스가 10인 행부터 13인 행의 country, lifeExp, gdpPercap열 데이터를 추출해라


```python
df.loc[range(10,14),['country','lifeExp','gdpPercap']]
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>lifeExp</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10</th>
      <td>Afghanistan</td>
      <td>42.129</td>
      <td>726.734055</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Afghanistan</td>
      <td>43.828</td>
      <td>974.580338</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Albania</td>
      <td>55.230</td>
      <td>1601.056136</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Albania</td>
      <td>59.280</td>
      <td>1942.284244</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[10:13,['country','lifeExp','gdpPercap']]
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>lifeExp</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10</th>
      <td>Afghanistan</td>
      <td>42.129</td>
      <td>726.734055</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Afghanistan</td>
      <td>43.828</td>
      <td>974.580338</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Albania</td>
      <td>55.230</td>
      <td>1601.056136</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Albania</td>
      <td>59.280</td>
      <td>1942.284244</td>
    </tr>
  </tbody>
</table>
</div>
<P style ="vertical-align: bottom; text-align: right;">출처:Do it! 데이터 분석을 위한 판다스 입문</p>
