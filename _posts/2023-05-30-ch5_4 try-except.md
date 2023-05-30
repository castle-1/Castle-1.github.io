# 예외처리

- 오류를 무시하고 싶을때
- try, except를 사용하여 예외적으로 오류를 처리할 수 있다.

### 오류는 어떨 때 발생?

- 디렉토리 안에 없는 파일을 열려고 시도할 때
- FileNotFoundError


```python
f = open('없는파일' , 'r')
```


    ---------------------------------------------------------------------------

    FileNotFoundError                         Traceback (most recent call last)

    Cell In[1], line 1
    ----> 1 f = open('없는파일' , 'r')


    File /opt/homebrew/Caskroom/miniconda/base/envs/yeardream/lib/python3.9/site-packages/IPython/core/interactiveshell.py:282, in _modified_open(file, *args, **kwargs)
        275 if file in {0, 1, 2}:
        276     raise ValueError(
        277         f"IPython won't let you open fd={file} by default "
        278         "as it is likely to crash IPython. If you know what you are doing, "
        279         "you can use builtins' open."
        280     )
    --> 282 return io_open(file, *args, **kwargs)


    FileNotFoundError: [Errno 2] No such file or directory: '없는파일'


- 0으로 다른 숫자를 나누는 경우
- ZeroDivisionError


```python
4 / 0
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    Cell In[2], line 1
    ----> 1 4 / 0


    ZeroDivisionError: division by zero


- 리스트에서 얻을 수 없는 값을 얻으려할 때
- IndexError


```python
a = [1,2,3]
a[4]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    Cell In[3], line 2
          1 a = [1,2,3]
    ----> 2 a[4]


    IndexError: list index out of range


## 오류 예외처리 기법

>try, except
>>try:<br>...<br>except[발생오류[as 오류 메시지 변수]]:<br>...

- try 블록 수행중 오류가 발생하면 except블록이 수행된다.
- try 블록에서 오류가 발생하지 않는다면 except블록은 수행되지 않는다.

### excpeet 구문
> except[발생오류[as 오류메시지 변수]]:
>> 괄호안의 내용은 생략할 수 있다. 관례 표기법이다.

#### except 사용방법 3가지
- try-except만 쓰는 방법
    * 종류 상관없이 오류가 발생하면 except블록을 수행
    >try:<br>...<br>except:<br>...

- 발생 오류만 포함한 except문
    * 오류가 발생했을 때 except문에 미리 정해 놓은 오류 이름과 일치할 때만 except블록을 수행
    >try:<br>...<br>except 발생오류:<br>...
    
- 발생 오류와 오류 매시지 변수까지 포함함 except문
    * 오류 메시지의 내용까지 알고 싶을 때 사용
    >try:<br>...<br>except 발생 오류 as 오류 메시지 변수:<br>...    

ex)발생 오류와 오류 매시지 변수까지 포함함 except문


```python
try:
    4/0
except ZeroDivisionError as e:
    print(e)
```

    division by zero


#### try-finally

- finally절은 try문 수행 도중 예외 발생 여부에 상관없이 항상 수행된다.
- 보통 finally절은 사용한 리소스를 close해야 할 때 많이 사용한다.


```python
f = open('foo.txt', 'w')
try:
    #수행문
finally:
    f.close()
```

- try문을 수행한 수 에외 발생 여부와 상관없이 finally절에서 f.close() 수행

#### 여러 개의 오류 처리하기
- try문 안에서 여러 개의 오류를 처리하기 위해 다음 구문사용

>try:<br>...<br>except 발생 오류 1:<br>...<br>except 발생 오류 2:<br>...

ex)0으로 나누는 오류와 인덱싱 오류


```python
try:
    a = [1,2]
    print(a[3])
    4/0
except ZeroDivisionError:
    print('0으로 나눌 수 없습니다.')
except IndexError:
    print('인덱싱할 수 없습니다.')
```

    인덱싱할 수 없습니다.


- 인덱싱 오류가 먼저 발생했기 때문에 4/0으로 발생되는 ZeroDivisionError 오류는 발생하지 않는다. 

#### 오류 메시지 가져오기
ex)


```python
try:
    a = [1,2]
    print(a[3])
    4/0
except ZeroDivisionError as e:
    print(e)
except IndexError as e:
    print(e)
```

    list index out of range


#### 하나의 except문으로 처리
ex) 두개 이상의 오류 동시처리


```python
try:
    a = [1,2]
    print(a[3])
    4/0
except (ZeroDivisionError, IndexError) as e:
    print(e)
```

    list index out of range


## 오류 회피하기
- 오류가 발생할 경우 그냥 통과시켜야 하는 경우


```python
try:
    f = open('없는파일','r')
except FileNotFoundError:
    pass
```

- pass를 사용하여 오류를 회피

## 오류를 일부러 발생시키기

- 일부러 오류를 발생시켜야 할 경우도 발생
- `raise` 명령어를 사용해 오류를 강제로 발생시킬 수 있다.

ex) Bird 클래스를 상속받는 자식 클래스는 반드시 fly함수를 구현해야 한다.


```python
class Bird:
    def fly(self):
        raise NotImplementedError
```

- 만약 자식 클래스에서 fly함수를 구현하지 않는다면 raise문에 의해 NotImplementedError 발생
- NotImplementedError : 파이썬 내장 오류, 꼭 작성해야 하는 부부이 구현되지 않았을 경우 일부러 오류를 일으키기 위해 사용


```python
class Eagle(Bird):
    pass
eagle = Eagle()
eagle.fly()
```


    ---------------------------------------------------------------------------

    NotImplementedError                       Traceback (most recent call last)

    Cell In[14], line 4
          2     pass
          3 eagle = Eagle()
    ----> 4 eagle.fly()


    Cell In[13], line 3, in Bird.fly(self)
          2 def fly(self):
    ----> 3     raise NotImplementedError


    NotImplementedError: 


- 반드시 fly함수를 구현해야 한다.


```python
class Eagle(Bird):
    def fly(self):
        print('Eagle is very fast')
    
eagle = Eagle()
eagle.fly()
        
```

    Eagle is very fast


## 예외 만들기

- 프로그램 수행 도중 특수항 경우에만 예외 처리를 하기 위해서 종종 예외를 만들어서 사용하기도 한다.
- 예외는 파이썬 내장 클래스인 `Exception 클래스`를 상속하여 만들 수 있다.


```python
class Myerror(Exception):
    pass
```

ex) 별명 출력 함수


```python
def say_nick(nick):
    if nick =='바보':
        raise Myerror()
    print(nick)
    
say_nick('천사')
say_nick('바보')
```

    천사



    ---------------------------------------------------------------------------

    Myerror                                   Traceback (most recent call last)

    Cell In[18], line 7
          4     print(nick)
          6 say_nick('천사')
    ----> 7 say_nick('바보')


    Cell In[18], line 3, in say_nick(nick)
          1 def say_nick(nick):
          2     if nick =='바보':
    ----> 3         raise Myerror()
          4     print(nick)


    Myerror: 


- '천사'가 출력후 Myerror 발생
- 예외 처리 기법으로 Myerror 발생 예외 처리


```python
try:
    say_nick('천사')
    say_nick('바보')
except Myerror:
    print('허용되지 않는 별명입니다.')
```

    천사
    허용되지 않는 별명입니다.


- 오류 메시지 사용하여 출력


```python
try:
    say_nick('천사')
    say_nick('바보')
except Myerror as e:
    print(e)
```

    천사
    


- 하지만 print(e)가 출력되지 않는다.
- 메시지가 보이게 하려면 오류 클래스에 `__str__ 메서드`를 구현해야 한다.
- `__str__ 메서드`는 print(e) 처럼 오류 메시지를 print문으로 출력할 경우에 호출되는 메서드


```python
class Myerror(Exception):
    def __str__(self):
        return '허용되지 않는 별명입니다.'

try:
    say_nick('천사')
    say_nick('바보')
except Myerror as e:
    print(e)
```

    천사
    허용되지 않는 별명입니다.

