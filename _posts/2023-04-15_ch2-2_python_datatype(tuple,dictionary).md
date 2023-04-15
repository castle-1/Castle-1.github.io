---
layout: single
title:  "첫 포스팅입니다. 설레네요!"
---
# 튜플 자료형

- 튜플은 몇 가지를 제외하고는 리스트와 거의 비슷하다.
- 리스트는 [] , 튜플은 { }로 둘러싼다.
- 리스트는 값의 생성,삭제,수정이 가능하지만 튜플은 값을 바꿀 수 없다.


```python
t1 =()
t2 = (1,) # 튜플은 한개의 요소만 가질때 요소 뒤에 ','를 반드시 붙여야한다.
t3 = (1,2,3)
t4 = 1,2,3 # 괄호를 생략해도 무방하다.
t5 = ('a','b',('ab','cd'))
print(t1)
print(t2)
print(t3)
print(t4)
print(t5)

```

    ()
    (1,)
    (1, 2, 3)
    (1, 2, 3)
    ('a', 'b', ('ab', 'cd'))


 - #### 프로그래밍 할 때 튜플과 리스트는 구별해서 사용하는것이 유리.
 - #### 프로그램이 실행될 동안 값이 항상 변하지 않기를 바란다면 튜플을 사용.
 - #### 프로그램이 실행될 동안 값이 수시로 변화시켜야할 경우 리스트사용.
 - #### 평균적으로 값이 변경되는 형태의 변수가 많기 때문에 튜플보다 리스트를 더 많이 사용한다.

### 튜플의 오솟값을 지우거나 변경하려면?

- 결과적으로 튜플의 요솟값은 한 번 정하면 지우가나 변경할 수 없다.

1. 튜플의 요솟값 삭제 할때


```python
t1 = (1,2,'a','b')
del t1[0]
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[3], line 2
          1 t1 = (1,2,'a','b')
    ----> 2 del t1[0]


    TypeError: 'tuple' object doesn't support item deletion


2. 튜플 요솟값 변경


```python
t1[0] = 'c'
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[4], line 1
    ----> 1 t1[0] = 'c'


    TypeError: 'tuple' object does not support item assignment


### 튜플 다루기
- 튜플은 값을 변화시키는 점만 빼면 리스트와 완전동일

1. 인덱싱


```python
t1 = (1,2,'a','b')
t1[0]
```




    1




```python
t1[3]
```




    'b'



2. 슬라이싱 


```python
t1[1:] # t1[1]부터 끝까지
```




    (2, 'a', 'b')



3. 튜플 더하기


```python
t2 = (3,4)
t1 + t2
```




    (1, 2, 'a', 'b', 3, 4)



4.튜플 곱하기


```python
t2*3
```




    (3, 4, 3, 4, 3, 4)



5.튜플 길이 구하기


```python
len(t1)
```




    4



# 딕셔너리 자료형
- 연관 배열 또는 해시라고한다.
- key-value를 한 쌍으로갖는 자료형.
- 리스트나 튜플처러 순차적으로 요솟값을 구하지 않고 key를 통해 value를 찾는다.
- ex) soccer 를 사전에서 찾을때 사전 맨 처음부터 순차적으로 찾지않고 soccer라는 단어가 있는 곳만 펼처본다.

### 딕셔너리 만들기
>{key1:value1, key2:value2, key3:value3, ..., key4:value4}


```python
dic = {'name':'castle1', 'pone':'01012345678', 'birth':'0709'}
dic
```




    {'name': 'castle1', 'pone': '01012345678', 'birth': '0709'}




```python
#key : 1, value hi
a = {1:'h1'}
a[1]
```




    'h1'




```python
#딕셔너리에 리스트 넣기
a = {'a':[1,2,3]}
a['a']
```




    [1, 2, 3]



### 딕셔너리 쌍 추가, 삭제 

1. 딕셔너리 쌍 추가

>딕셔너리명[key] = value


```python
a = {1:'a'}
a[2] = 'b'# 2->key 'b'->value
a
```




    {1: 'a', 2: 'b'}




```python
a['name'] = 'castle1'
a
```




    {1: 'a', 2: 'b', 'name': 'castle1'}




```python
a[3] = [1,2,3]
a
```




    {1: 'a', 2: 'b', 'name': 'castle1', 3: [1, 2, 3]}



2. 딕셔너리 요소 삭제 

>del 딕셔너리명[key]


```python
del a[1]
a
```




    {2: 'b', 'name': 'castle1', 3: [1, 2, 3]}



### 딕셔너리 사용하는 방법

1. 딕셔너리에서 key를 사용해서 valu얻기
>리스트, 튜플은 요솟값을 얻을때 인덱싱, 슬라이싱을 사용해야하지만 딕셔너리는 key를 사용해서 요솟값(value)를 쉽게 구할 수 있다.
>>딕셔너리명[key]


```python
grade = {'pey' : 10, 'jullet': 99}
grade['pey']
```




    10



2. 딕셔너리 생성시 주의할점
>딕셔너리에서 key는 '고유한값'이다. 따라서 key를 중복설정하면 하나를 제외한 나머지는 전부 무시!
>>동일한 key가 존재하면 어떤 key에 해당하는 value를 불러야할지 알 수 없다.


```python
a = {1:'a', 1:'b'}
a # 1:'a' 가 무시되었다.
```




    {1: 'b'}



>key에는 리스트를 사용할 수 없지만 튜플은 사용가능하다.
>>리스트는 값이 변할 수 있고 튜플은 값이 변하지 않기때문이다.


```python
a = {[1,2]:'a'} # 리스트를 키로 사용
a
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[24], line 1
    ----> 1 a = {[1,2]:'a'}
          2 a


    TypeError: unhashable type: 'list'


### 딕셔너리 관련 함수

1. key 리스트 만들기
>딕셔너리명.key()
>>딕셔너리의 key만 모아서 dic_keys객체로 반환


```python
a = {'name':'castle1', 'phone':'01012345678', 'birth':'0709'}
a.keys()
```




    dict_keys(['name', 'phone', 'birth'])



2. dict_keys를 리스트로 변환하기


```python
list(a.keys())
```




    ['name', 'phone', 'birth']



3. value 리스트 만들기
>딕셔너리명.values()
>>key와 마찬가지로 dic_values객체로 반환


```python
a.values()
```




    dict_values(['castle1', '01012345678', '0709'])



3. key, value 쌍 얻기(item)
>딕셔너리명.items()
>>key, value의 쌍을 '튜플'로 묶은 값을 dic_items객체로 반환


```python
a.items()
```




    dict_items([('name', 'castle1'), ('phone', '01012345678'), ('birth', '0709')])



4. key:value 쌍 모두 지우기(clear)
>딕셔너리명.clear()
>>딕셔너리 모든 요소 삭제, 빈딕셔너리는 {}로 표현


```python
a.clear()
a
```




    {}



5.key로 value 얻기(get)
>딕셔너리명.get(key)
>>key에 대응하는 value를 반환한다. , 존재하지 않는 key로 값을 가져오면 key오류 발생, 딕셔너리명.get(key)를 사용하면 None를 반환


```python
a = {'name':'castle1', 'phone':'01012345678', 'birth':'0709'}
print(a.get('name'))
print(a.get('phone'))
```

    castle1
    01012345678



```python
print(a.get('height'))
```

    None



```python
print(a['height'])
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    Cell In[35], line 1
    ----> 1 print(a['height'])


    KeyError: 'height'


6.딕셔너리 디폴트값 반
>딕셔너리에서 찾는 값이 없을 경우 미리 정해둔 디폴트 값을 대신가져오 할 수 있다.
>>get.(key,디폴트값)


```python
a.get('height','176') #a 딕셔너리에는 height가 없기때문에 디폴트로 미리 정해둔 176이 출력
```




    '176'



6. 해당 key가 딕셔너리 안에 있는지 조사하기(in)


```python
'name' in a
```




    True




```python
'height' in a
```




    False
<P style ="vertical-align: bottom; text-align: right;">출처:점프 투 파이썬</p>


