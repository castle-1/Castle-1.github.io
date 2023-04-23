---
layout: single
title:  "ch4. 파이썬 함수"
categories : python
---
# 함수

- 입력값을 가지고 어떤 일을 수행한 다음에 그 결과물을 내어놓는것.

### 함수를 사용하는 이유
- 반복되는 부분이 있을경우 반복적으로 사용되는 가치있는 부분을 한 뭉치로 묶는것.
- 어떤 입력값을 주었을 때 어떤 결괏값을 돌려준다.
- 프로그램을 함수화 하면 프로그램을 일목요연하게 볼 수 있다.


### 파이썬 함수 구조
- def 는 함수를 만들때 사용하는 예약어
- 함수 이름은 함수를 만드는 사람이 임의로 설정 가능
- 괄호안 안의 매개변수는 이 함수에 입력으로 전달되는 값을 받는 변수.

>표현법
>>def 함수이름(매개변수): <br> 수행할문장1 <br> 수행할문장2<br>


```python
# ex) 함수의 이름 : add, 입력으로 2개의 값을 받고 입력받은 2개의 수를 더해서 반환

def add(a,b):
    return a+b # return은 결괏 값을 돌려주는 명령어

c = add(1,2) # c변수에 함수를 호출해서 return으로 반환된 값을 c에 저장
print(c)
```

    3


### 매개변수와 인수

- 매개변수(parameter)
- 인수(arguments)
- 매개변수와 인수는 헷갈리는 용어로 주의하기!
- 매개변수는 함수에 입력으로 전달된 값을 받는 변수
- 인수는 함수를 호출할 때 전달하는 입력값


```python
# ex) 매개변수와 인수
def add(a,b): #a,b 는 매개변수
    return a+b
print(add(3,4)) #3,4 는 인수
```

    7


### 입력값과 결괏값에 따른 함수의 형태
- 함수는 들어온 입력값을 받아 어떤 처리를 하여 적절한 결괏값을 돌려준다.
- 함수의 형태는 입력값과 결괏값의 존재 유무에 다라 4가지 유형으로 나눈다.
- 일반적인 함수, 입력값이 없는 함수, 결괏값이 없는 함수, 입력값과 결괏값이 모두 없는 함수

#### 일반적인 함수
- 입력값과 결괏값이 모두 있는함수

>표현법(.... -> 들여쓰기)
>>def 함수이름(매개뱐수):<br>....수행할문장<br>....수행할문장<br>....return 결괏값


```python
# 일반적인 함수
def add(a,b):
    result = a+b
    return result
print(add(3,4))
```

    7


- 입력값과 결괏값이 있는 함수의 사용법
- 결괏값을 받을 변수 = 함수이름(입력인수1, 입력인수2,...,입력인수n)

#### 입력값이 없는 함수 


```python
#입력값이 없는 함수
def say():
    return 'hi'
a = say()
print(a)
```

    hi


- 위의 say()함수를 쓰기 위해서는 괄호안에 아무 매개변수를 넣지 않아야한다.
- say()함수는 입력값이 없지만 결괏값 hi를 돌려준다.
- 입력값이 없고 결괏값만 있는 함수 사용법
- 결괏값을 받을 변수 = 함수이름()

#### 결괏값이 없는 함수 


```python
# 결과값이 없는 함수
def add(a,b):
    print(f'{a}, {b}의 합은 {a+b}입니다.')
add(3,4)
```

    3, 4의 합은 7입니다.


- 결괏값이 없는 함수 사용법
- 함수이름(입력인수1, 입력인수2,..입력인수n)


```python
#결괏값이 없는지 확인하기
a = add(3,4)
```

    3, 4의 합은 7입니다.


- print문의 출력값은 결괏값이 아니다!
- print문은 함수의 구성요소중 하나인 수행할 문장에 해당하는부분
- 결괏값은 없다. 결괏값은 오직 return 명령어로만 돌려받을 수 있다.


```python
print(a)
```

    None


- none는 거짓을 나타내는 자료형.
- 결괏값이 없을때 a=add(3,4)처름 쓰면 함수의 반환값으로 a변수에 none을 돌려준다.

#### 입력겂도 결괏값도 없는 함수 


```python
def say():
    print('hi')

say()
```

    hi


- 입력인수인 매개변수도 없고 return문도 없으니 입력값도 결괏값도 없는 함수이다.
- 입력값도 결괏값도 없는 함수 사용법
- 함수이름()

### 매개변수 지정하여 호출하기

- 함수호출시 매개변수를 지정할 수 있다.


```python
def add(a, b):
    return a+b
result = add(a=3,b=5) # a에 3을, b에 5를 전달
print(result)
```

    8


- 매개변수르 지정하면 순서에 상관없이 사용할 수 있다.


```python
result2 = add(b=1, a=2)
print(result2)
```

    3


## 입력값이 몇 개가 될지 모를때
- 일반함수 형태에서 괄호안의 매개변수 부분에 '*메개변수'로 사용

>표현법
>>def 함수이름(*매개변수):<br>....수행할문장1<br>....수행할문장2

#### 여러개의 입력값을 받는 함수 만들기 


```python
def add_many(*args):
    result = 0
    for i in args:
        result = result+i
    return result


result = add_many(1,2)
result2 = add_many(1,2,3)
result3 = add_many(1,2,3,4,5,6,7,8,9,10)

print(result)
print(result2)
print(result3)
```

    3
    6
    55


- *args 처럼 매개변수앞에 *을 붙이면 입력값을 전부 모아 '튜플'로 만들어준다.
- *args는 임의로 정한 변수이름 임의대로 변경하여도 무방하다.

#### 함수의 매개변수로 *args만 사용할 수 있는 것은 아니다.


```python
def add_mul(choice,*args):
    if choice == 'add':
        result = 0
        for i in args:
            result+=i
    elif choice =='mul':
        result = 1
        for i in args:
            result*=i
    return result

result = add_mul('add',1,2,3,4,5)
result2 = add_mul('mul',1,2,3,4,5)

print(result)
print(result2)
            
```

    15
    120


#### 매개변수 앞에 **을 붙이면 딕셔너리 형태로 저장된다. 


```python
def print_kwargs(**kwargs):
    print(kwargs)
    
print_kwargs(a=1)
print_kwargs(name = 'wsi', age = 31)
```

    {'a': 1}
    {'name': 'wsi', 'age': 31}


### 함수의 결괏값은 어제나 하나이다


```python
def add_and_mul(a,b):
    return a+b,a*b

result = add_and_mul(3,4)
print(result)
```

    (7, 12)


- 결괏값이 a+b, a*b 2개이지만 결괏값을 받는 변수는 result 하나라서 오류가 발생하지 않을까 의문이든다.
- 하지만 오류는 발생하지 않는다.
- 이유는 함수의 결괏값은2개가 아니라 언제나 1개 라는데 있다.
- add_and_mul 함수의 결괏값 a+b, a*b는 튜플값 하나인 (a+b,a*b)로 돌려준다.


```python
#하나의 튜플값을 2개의 결괏값처럼 받고 싶을 경우
result1, result2 = add_and_mul(3,4) # result1, result2 = (7,12), result1 = 7, result2 = 12
print(result1)
print(result2)
```

    7
    12


#### return을 2번 쓴다면?


```python
def add_and_mul(a,b):
    return a+b
    return a*b

result = add_and_mul(3,4)
print(result)
```

    7


- 두 번째 return문인 return a*b는 실행되지 않는다.
- 즉, 함수는 return을 만나는 순간 결괏값을 돌려준 다음 함수를 빠져나가게된다.
- 특별한 상황일 때 함수를 빠져나가고 싶다면 return을 단독으로 사용하여 함수를 즉시 빠져나갈 수 있다.
- return을 단독으로 써서 함수를 빠져나가는 방법은 실제 프로그래밍에서 자주 사용된다.

### 매개변수에 초깃값 미리 설정하기 


```python
def say_myself(name, old, man=True):
    print(f'나의 이름은 {name}입니다.')
    print(f'나이는 {old}입니다.')
    if man:
        print('남자입니다.')
    else:
        print('여자입니다.')
        
say_myself('위성일',31)
say_myself('위성일',31,True) # man 이라느 변수에 입력값을 주지않아도 초깃값으로 True라고 설정되어 있어서 같은 결과를 출력
say_myself('위성일',31,False)
```

    나의 이름은 위성일입니다.
    나이는 31입니다.
    남자입니다.
    나의 이름은 위성일입니다.
    나이는 31입니다.
    남자입니다.
    나의 이름은 위성일입니다.
    나이는 31입니다.
    여자입니다.


- 함수의 매개변수 초깃값을 설정하는 방법
- man = True 처럼 매개변수에 미리 값을 할당
- 함수의 매개변수에 들어갈 값이 항상 변하는 것이 아닐 경우 함수의 초깃값을 미리 설정하면 유용하다.


```python
# 초깃값을 설정시 주의할점
def say_myself(name, man=True, old): # old와 man의 위치를 서로 바꿈
    print(f'나의 이름은 {name}입니다.')
    print(f'나이는 {old}입니다.')
    if man:
        print('남자입니다.')
    else:
        print('여자입니다.')

say_myself('위성일',31) # 파이썬 인터프리터는 31을 man변수와 old 변수중 어느곳에 대입해야할지 알 수 없다.
```


      Cell In[37], line 2
        def say_myself(name, man=True, old): # old와 man의 위치를 서로 바꿈
                                       ^
    SyntaxError: non-default argument follows default argument



- 초깃값을 설정해 놓은 매개변수 뒤에 초깃값을 설정해 놓지 않은 매개변수는 사용할 수 없다.
- 즉, 매개변수로 (name, old, man=True)는 가능하지만 (name, man=True, old)는 불가능하다.
- 초기화 시키고 싶은 매개변수는 항상 뒤쪽에 위치해야한다.

### 함수 안에서 선언한 변수의 효력 범위


```python
a = 1
def vartest(a): #함수 안에서 만든 매개변수는 함수 안에서만 사용가능한 '함수만의 변수' 
    a = a+1     #즉, 함수밖의 a=1 의 a와 vartest안의 매개변수 a는 같지않다.
                #함수 안에서 사용하는 매개변수는 함수 밖의 변수 이름과는 전혀 상관없다.
vartest(a)
print(a)
```

    1



```python
def vartest2(b): 
    b=b+1

vartest2(b)
print(b) # 에러나는 이유는 print(b)에 입력받아야할 변수b를 어디서든 찾을 수 없기 때문이다.
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[39], line 4
          1 def vartest2(b):
          2     b=b+1
    ----> 4 vartest2(b)
          5 print(b)


    NameError: name 'b' is not defined


#### 함수 안에서 함수 밖의 변수를 변경하느 방법

1, return 사용하기


```python
c = 1
def vartest3(c):
    c = c+1
    return c

c = vartest3(c) # vartest3의 결괏값을 변수c에 저장, 여기서 vartest안의 변수c와 밖의c는 다른 것이다.
print(c)
```

    2


2. golbal 명령어 사용하기


```python
d = 1
def vartest4():
    global d #함수 밖의d 변수를 직접 사용
    d=d+1

vartest4()
print(d)
```

    2


- 프로그래밍 할대 global 명령어는 사용하지 않는게 좋다.
- 함수는 독립적으로 존재하는 것이 좋기 때문
- 와부 변수에 종속적인 함수는 좋은 함수가 아니다.
- global 명령어는 사용하는 방법은 피하고 return을 사용하는 것이 좋다.

###  lambda
- lambda는 함수를 생성할 떼 사용하는 예약어로 def와 동일한 열학을 한다.
- 함수를 한 줄로 간결하게 만들때 사용.
- def를 사용해야 할 정도로 복잡하지 않거나 def를 사용할 수 없는곳에 주로 쓰인다.

>표현법
>>lambda 매개변수1,매개변수2,..,매개변수n:매개변수를 사용한 표현식


```python
add = lambda a,b: a+b
result = add(3,4)
print(result)
```

    7



```python

```
<P style ="vertical-align: bottom; text-align: right;">출처:점프 투 파이썬</p>
