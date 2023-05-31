# 파이썬 내장함수(python Built-in functions)(2)

### max
- `max(iterable)` 인수로 반복가능한 자료형을 입력 받아 최댓값을 돌려주는 함수  


```python
print(max([1,2,3]))
print(max('python'))
```

    3
    y


### min
- `min(iterable)` 은 max와 반대로 인수로 반복가능한 자료형을 받아 최솟값을 돌려주는 함수


```python
print(min([1,2,3]))
print(min('python'))
```

    1
    h


### oct
- `oct(x)`는 정수 형태의 숫자랄 8진수 문자열로 돌려주는 함수


```python
print(oct(34))
print(oct(12345))
```

    0o42
    0o30071


### open

- `open(file name,[mode])` 은 파일이름과 읽기방법을 입력받아 파일 객체르 돌려주는 함수
- 읽기방법을 생략하면 기본값인 읽기 전용모드(r)로 파일 객체를 만들어 돌려준다.
- w : 쓰기 모드로 파일열기
- r : 읽기 모드로 파일열기
- a : 추가 모드로 파일열기
- b : 바이너리 모드로 파일열기
- `b는 w,r,a`와 함께 사용


```python
# rb
f = open('binary_file', 'rb')
```


```python
# fread와 fread2는 동일한 방법, 

fread = open('read_mode.txt', 'r')
fread2 = open('read_mode.txt')
```


```python
# 추가모드(a)

fappend = open('append_mode,txt','a')
```

###  ord
- `ord(c)`는 문자의 아스키 코드 값을 돌려주는 함수


```python
print(ord('a'))
print(ord('0'))
```

    97
    48


### pow
- `pow(x,y)`는 x의 y제곱한 결괏값을 돌려주는 함수


```python
print(pow(2,5))
print(pow(3,3))
```

    32
    27


### range
- `range([start], stop, [step])`는 for문과 함께 자주 사용하는 함수
- `range`함수는 입력받은 숫자에 해당하는 범위 값을 반복 가능한 객체로 만들어 돌려준다.

ex) 인수가 1개인 경우


```python
list(range(5))
```




    [0, 1, 2, 3, 4]



ex) 인수가 2개일 경우
- 2개의 인수는 시작 숫자와 끝 숫자를 나타낸다.


```python
list(range(5,10))
```




    [5, 6, 7, 8, 9]



### ex) 인수가 3개일 경우
- 3번째 인수는 숫자 사이의 거리를 말한다.


```python
list(range(1,10,2))
```




    [1, 3, 5, 7, 9]




```python
list(range(0,-10,-1))
```




    [0, -1, -2, -3, -4, -5, -6, -7, -8, -9]



###  round
- `round(number,[ndigits])`함수는 숫자를 입력받아 반올림 해주는 함수


```python
print(round(4.6))
print(round(4.2))
```

    5
    4


- 소수점 2자리 까지만 반올림하여 표시할 수 있다.


```python
print(round(5.678,2))
```

    5.68


### sorted
- `sorted(iterable)`함수는 입력값을 정렬한 후 그 결과를 리스트로 돌려주는 함수
- 리스트 자료형에도 sort함수가 있다. 하지만 리스트 자료형의 sort함수는 리스트 객체 그 자체를 정렬만 할 뿐 정렬된 결과를 돌려주지는 않는다.


```python
print(sorted([3,1,2]))
print(sorted(['a','c','b']))
print(sorted('zero'))
print(sorted((3,2,1)))
```

    [1, 2, 3]
    ['a', 'b', 'c']
    ['e', 'o', 'r', 'z']
    [1, 2, 3]


### str 
- `str(object)`은 문자열 형태로 객체를 변환하여 돌려준다.


```python
print(str(3))
print(str('hi'))
print(str('hi'.upper())) # upper은 대문자로 만들어준다.
```

    3
    hi
    HI


### sum
- `sum(iterable)`은 입력받은 리스트나 튜플의 모든 요소의 합을 돌려주는 함수


```python
print(sum([1,2,3]))
print(sum((4,5,6)))
```

    6
    15


### tuple
- `tuple(iterable)`은 반복 가능한 자료형을 입력받아 튜플 형태로 바꾸어 돌려주는 함수
- 만약 튜플이 입력으로 들어오면 그대로 돌려준다.


```python
print(tuple('abc'))
print(tuple([1,2,3]))
print(tuple((1,2,3)))
```

    ('a', 'b', 'c')
    (1, 2, 3)
    (1, 2, 3)


### type
- `type(object)`은 입력값의 자료형이 무엇인지 알려주는 함수


```python
print(type('abc'))
print(type([]))
print(type(open('test','w')))
```

    <class 'str'>
    <class 'list'>
    <class '_io.TextIOWrapper'>


### zip
- `zip(*iterable)`은 동일한 개수로 이루어진 자료형을 묶어주는 역할을 하는 함수


```python
print(list(zip([1,2,3],[4,5,6])))
print(list(zip([1,2,3],[4,5,6],[7,8,9])))
print(list(zip('abc','def')))
```

    [(1, 4), (2, 5), (3, 6)]
    [(1, 4, 7), (2, 5, 8), (3, 6, 9)]
    [('a', 'd'), ('b', 'e'), ('c', 'f')]

