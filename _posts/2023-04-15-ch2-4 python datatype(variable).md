---
layout: single
title:  "ch2-4. 파이썬데이터 타입(variable)"
categories : python
---
# 변수
<br>

>변수 만들기
>> 변수이름 = 변수에 저장할 값

- 다른 프로그래밍 언어인 c나 java에서는 변수 선언시 자료형을 직접 지정해야한다.
- 파이썬은 변수에 저장된 값을 보고 스스로 판단하여 자료형을 지정한다.

### 변수란?
- 파이썬에서 변수는 객체를 가리키는것
- 객체는 지금껏 보아온 자료형과 같은것을 의미
>a = [1,2,3]
>>[1,2,3]을 가지는 리스트 자료형(객체)이 자동으로 메모리에 생성되고<br> 변수 a는[1,2,3]리스트가 저장된 메모리를 가리키게 된다.

- a가 가리키는 메모리 주소 확인하기
>id(변수명)
>>id함수는 변수가 가리키고 있는 객체의 주소값을 돌려주는 파이썬 내장함수


```python
a = [1,2,3]
id(a) # 즉 변수 a가 가리는 [1,2,3]의 주소는 140404662463360
```




    140404662463360



### 리스트를 복사할때


```python
a = [1,2,3]
id(a) # a가 가리키는 주소는 140404662468736
```




    140404662468736




```python
b = a # a와 b의 주소가 같아졌다. 즉, a가 가리키는 대상과 b가 가리키는 대상이 같아졌다.
print(id(b))
print(id(a))
```

    140404662468736
    140404662468736


- 동일한 객체를 가리키고 있는지 판단하는 파이썬 명령어
>is
>>ex) a is b


```python
a is b #a와 b가 동일한 객체르 가지고있는지 확인
```




    True




```python
a[1] = 4
a
```




    [1, 4, 3]




```python
b
```




    [1, 4, 3]



- 리스트 a의 2번째 요소를 바꾸었고 b또한 같이 바뀐걸 확인할 수 있다.
- a와 b 모두 동일한 객체를 가리키고있기 때문이다.

### b변수를 생성할때 a변수의 값을 가져오면서 a와 다른 주소를 가리키도록 만들기 
<br>
1.리스트 전체를 가리키는 [:] 사용하기



```python
a = [1,2,3]
b = a[:] #리스트 a의 처음 요소부터 끝가지 슬라이싱
a[1] = 4
a
```




    [1, 4, 3]




```python
b
```




    [1, 2, 3]



2. copy 모듈 사용


```python
from copy import copy
a = [1,2,3]
b = copy(a) # b=a[:]동일한 표현
b
```




    [1, 2, 3]




```python
print(a)
print(b)
print(a is b) # 동일한 객체가 아님을 알 수 있다.
```

    [1, 2, 3]
    [1, 2, 3]
    False


### 변수를 만드는 여러가지 방법


```python
a, b = ('python', 'funny') # 튜플로 대입
print(a)
print(b)
```

    python
    funny



```python
(a,b) = 'python', 'funny' #튜플은 () 생략가능, 위와 동일한 표현
print(a)
print(b)
```

    python
    funny



```python
[a,b] = ['python', 'funny'] # 리스트로 만들기
print(a)
print(b)
```

    python
    funny



```python
a = b = 'python' # 여러 개의 변수에 갑은 값을대입
print(a)
print(b)
```

    python
    python



```python
a = 3
b = 5
a, b = b ,a #a와 b의 값을 바꾸기
print(a)
print(b)
```

    5
    3



```python

```
