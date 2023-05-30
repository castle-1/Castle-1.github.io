---
layout: single
title:  "ch5_5. 내장함수(python Built-in functions)(1)"
categories : python
---

# 파이썬 내장함수(python Built-in functions)

- 새로운 프로그램을 만들기 전에는 이미 만들어진 것들, 그중에서도 특히 파이썬 배포본에 함께 들어 있는 파이썬 라이브러리를 살펴보는 것이 매우 중요하다.
- 파이썬 내장 함수는 외부 모듈과 달리 import가 필요하지 않기 때문에 아무런 설정 없이 바로 사용할 수 있다.

### abs
- 숫자를 입력받았을때 절댓값으로 돌려주는 함수


```python
print(abs(3))
print(abs(-3))
print(abs(-1.23))
```

    3
    3
    1.23


### all
- `all(x)`는 반복가능한 자료형 x를 입력 인수로 받아 x가 모두 참이면 true, 거짓이 하나라도 있으면 false를 돌려준다.


```python
print(all([1,2,3]))
print(all([0,1,2,3])) # 0은 false
```

    True
    False


### any

- `any(x)`는 x중 하나라도 참이 있으면 true, x가 모두 거짓일대 false를 돌려준다.
- `all(x)의 반대`


```python
print(any([1,2,3,0]))
print(any([0,''])) # 0,''은 모두 거짓
```

    True
    False


### chr

- `chr(i)`는 아스키 코드 값을 입력받아 그 코드에 해당하는 문자를 출력


```python
print(chr(97)) # 아스키 코드 97은 소문자a
print(chr(48))
```

    a
    0


### dir
- `dir`은 객체가 자체적으로 가지고 있는 변수나 함수를 보여준다.

ex) 리스트와 딕셔너리 관련 함수


```python
print(dir([1,2,3]),'\n')
print(dir({'1','a'}))
```

    ['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort'] 
    
    ['__and__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__iand__', '__init__', '__init_subclass__', '__ior__', '__isub__', '__iter__', '__ixor__', '__le__', '__len__', '__lt__', '__ne__', '__new__', '__or__', '__rand__', '__reduce__', '__reduce_ex__', '__repr__', '__ror__', '__rsub__', '__rxor__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__xor__', 'add', 'clear', 'copy', 'difference', 'difference_update', 'discard', 'intersection', 'intersection_update', 'isdisjoint', 'issubset', 'issuperset', 'pop', 'remove', 'symmetric_difference', 'symmetric_difference_update', 'union', 'update']


### divmod 
- `divmod(a,b)`는 2개의 숫자를 입력으로 받는다.
- a를 b로 나눈 몫과 나머지를 튜플 형태로 돌려준다.


```python
divmod(7,3)
```




    (2, 1)



### enumerate

- 열거하다 라는 뜻
- 순서가 있는 자료형(리스트, 튜플, 문자열)을 입력받아 인덱스 값을 포함하는 `enumerate`객체를 돌려준다.
- enumerate를 for문과 함께 사용하면 자료형의 순서(index)와 그값을 쉽게 알 수 있다.
- for문 처럼 반복되는 구간에서 객체가 현재 어느 위치에 있는지 알려 주는 인덱스 값이 필요할 때 `enumerate 함수`를 사용하면 유용하다. 


```python
for i, name in enumerate(['body','foo','bar']):
    print(i, name)
```

    0 body
    1 foo
    2 bar


###  eval
- `eval(expression)`은 실행 가능한 문자열을 입력받아 문자열을 실행한 결괏값을 돌려준다.
- 입력받은 문자열로 파이썬 함수나 클래스를 동적으로 실행하고 싶을 때 사용


```python
print(eval('1+2'))
print(eval("'hi' + 'a'"))
print(eval('divmod(4,3)'))
```

    3
    hia
    (1, 1)


### filter
- `filter` : 무엇인가를 걸러낸다는 뜻, filter함수도 동일한 의미를 가진다.
- `filter 함수`는 첫 번째 잉ㄴ수로 함수 이름, 두 번째 인수로 그 함수에 차례로 들어갈 반복 가능한 자료형을 받는다.
- 두 번째 인수인 반복 가능한 자료형 요소가 첫 번째 인수인 함수에 입렵되었을때 반환 값이 참인 것만 묶어서 돌려준다.


```python
#리스트를 입렵받아 양수 판별
def positive(l):
    result = []
    for i in l:
        if i>0:
            result.append(i)
    return result
print(positive([1,-3,2,0,-5,6]))
```

    [1, 2, 6]



```python
#filter함수 사용
def positive(x):
    return x>0
print(list(filter(positive, [1,-3,2,0,-5,6])))
```

    [1, 2, 6]



```python
# lambda, filter 사용
list(filter(lambda x: x>0,[1,-3,2,0,-5,6]))
```




    [1, 2, 6]



### hex

- `hex(x)`는 정수 값을 입력 받아 16진수로 변환하여 돌려주는 함수


```python
print(hex(234))
print(hex(3))
```

    0xea
    0x3


### id  
- `id(object)`는 객체를 입력받아 객체의 고유 주소 값(레퍼런스)를 돌려주는 함수


```python
a = 3
print('a : ',id(a))
print('3 : ',id(3))

b = a
print('b : ', id(b))
```

    a :  4381141360
    3 :  4381141360
    b :  4381141360


- a,3,b 모두 같은 객체

### input
- `input([prompt])`은 사용자 입력을 받는 함수


```python
a = input()
```

    hi



```python
a
```




    'hi'




```python
b = input('enter : ')
```

    enter : b hi



```python
b
```




    'b hi'



### int 
- `int(x)`는 무낮열 형태의 숫자나 소수점이 있는 숫자 등을 정수 형태로 돌려주는 함수
- 정수를 입력받으면 그대로 돌려준다.


```python
print(int(3))
print(int('4'))
print(int(3.14))
```

    3
    4
    3


- int(x,radix) 
- radix : 진수로 표현된 문자열 x를 10진수로 변환하여 돌려준다.


```python
print(int('11',2)) # 2진수 11을 10잔수로 변환
print(int('1A',16)) #16진수 1A를 10진수로 변환
```

    3
    26


### isinstance

- `isinstance(object, class)`는 첫 번째 인수로 인스턴스, 두 번째 인수로 클래스 이름을 받는다.
- 입력으로 받은 인스턴스가 그 클래스의 인스턴스 인지를 판단하여 참이면 true, 거짓이면 false를 돌려준다.


```python
class person:
    pass

a = person()
print('a : ', isinstance(a,person))

b = 3
print('b : ', isinstance(b,person))
```

    a :  True
    b :  False


### len 
- `len(s)`은 입력값 s의 길이를 돌려주는 함수


```python
print(len('python'))
print(len([1,2,3]))
print(len((1,'a')))
```

    6
    3
    2


### list
- `list(S)`는 반복가능한 자료형 s를 입력받아 리스트로 만들어주는 함수
- `list 함수`에 리스트를 입력하면 똑같은 리스트를 복사하여 돌려준다.


```python
print(list('python'))
print(list((1,2,3)))
```

    ['p', 'y', 't', 'h', 'o', 'n']
    [1, 2, 3]


### map 
- `map(f,iterable)`은 함수(f)와 반복가능한 자료형을 입력받는다.
- map은 입력받은 자료형의 각 요소를 함수 f가 수행한 결과르 묶어서 돌려준다.


```python
# two times

def two_times(numberList):
    result = []
    for number in numberList:
        result.append(number*2)
    return result
result = two_times([1,2,3,4])
print(result)
```

    [2, 4, 6, 8]



```python
# map함수 사용
def two_times(x):
    return x*2
list(map(two_times,[1,2,3,4]))
```




    [2, 4, 6, 8]




```python
# lambda, map사용
list(map(lambda a: a*2,[1,2,3,4]))
```




    [2, 4, 6, 8]


<P style ="vertical-align: bottom; text-align: right;">출처:점프 투 파이썬</p>
