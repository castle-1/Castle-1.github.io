---
layout: single
title:  "ch4-3. 파일 읽고 쓰기"
categories : python
---
# 파일 읽고 쓰기

### 파일 생성하기

- 프로그램을 실행한 디렉터리에 새로운 파일이 하나 생성
- 파일을 생성하기 위해 파이썬 내장함수 open()을 사용
- `파일이름`과 `파일 열기 모드`를 입력값으로 받고 결괏값으로 파일 객체를 돌려준다.

>표현법
>>파일객체 = open('파일이름','파일 열기 모드')

#### 파일열기모드
- r : 읽기모드 - 파일을 일기만 할 때 사용
- w : 쓰기모드 - 파일에 내용을 쓸ㄷ 때 사용
- a : 차가모드 - 파일의 마지막에 새로운 내용을 추가할 때 사용

* 파일을 쓰기모드로 열면 해당 파일이 이미 존재할 경우 원래 있던 내용이 모두 사라진다.
* 해당 파일이 존재하지 않다면 새로운 파일이 생성된다.


```python
f = open('test.txt', 'w') # 파일읽기모드로 `w` 사용, 해당 디렉터리에 test.txt 파일이 없기때문에  새로 생성 
f.close
```




    <function TextIOWrapper.close()>


![open()_test](/assets/images/git_github_img/open()_test.png)

### 원하는 경로에 디렉터리 생성

>f = open('경로/파일이름.확장자', 'w')<br>f.close()

#### close()
- 열려 있는 객체를 닫아주는 역할
- 생략 가능
- 프로그램을 종료할때 파이썬 프로그램이 열려있는 파일의 객체를 자동으로 닫아준다.
- 하지만 `close()를 사용해서 열려있는 파일을 직접 닫아 주는것이 좋다.`
- 쓰기모드(w)로 열었던 파일을 닫지않고 다시 사용하려고 하면 오류가 발생할 수 있다.

### 파일을 쓰기모드로 열어 출력값 적기

- 파일에 결괏값을 적는 방법


```python
f = open('/Users/castle1/Posts/python/test.txt','w')
for i in range(1,11):
    data = '%d번째 줄입니다.\n' % i
    f.write(data)
f.close()
```
![open()_test_입력](/assets/images/git_github_img/open()_test_입력.png)
- 기존 방법


```python
for i in range(1,11):
    data = '%d번째 줄입니다.\n' % i
    print(data)
```

    1번째 줄입니다.
    
    2번째 줄입니다.
    
    3번째 줄입니다.
    
    4번째 줄입니다.
    
    5번째 줄입니다.
    
    6번째 줄입니다.
    
    7번째 줄입니다.
    
    8번째 줄입니다.
    
    9번째 줄입니다.
    
    10번째 줄입니다.
    


- 두 방법의 차이점은 print 대신 파일 객체 `f의 write함수를 사용`한 것 말고는 없다.

### 프로그램의 외부에 저장된 파일을 읽는 여러가지 방법

##### 1. `readline()`
    - test.txt 파일의 가장 첫 번째 줄 출력


```python
f = open('/Users/castle1/Posts/python/test.txt','r')
line = f.readline()
print(line)
f.close
```

    1번째 줄입니다.
    





    <function TextIOWrapper.close()>



#### readline()을 사용하여 모든줄 읽기


```python
f = open('/Users/castle1/Posts/python/test.txt','r')
while True:
    line = f.readline()
    if not line:
        break
    print(line)
f.close()
```

    1번째 줄입니다.
    
    2번째 줄입니다.
    
    3번째 줄입니다.
    
    4번째 줄입니다.
    
    5번째 줄입니다.
    
    6번째 줄입니다.
    
    7번째 줄입니다.
    
    8번째 줄입니다.
    
    9번째 줄입니다.
    
    10번째 줄입니다.
    


- 무한루프 안에서 r.readline()를 사용해서 한 줄씩 읽어드린다.
- 읽을 줄이 없으면 break수행
- readline()은 더이상 읽을 줄이 없으면 none를 출력

##### 2. `readlines()`

- `readlines()`함수는 파일의 모든 줄을 읽어서 각각의 줄을 요소로 갖는 `리스트`로 돌려준다.
- lines는 리스트 ['1번째 줄입니다.','2번째 줄입니다.',....,'10번째 줄입니다.']


```python
f = open('/Users/castle1/Posts/python/test.txt','r')
lines = f.readlines()
for line in lines:
    print(line)
f.close()
```

    1번째 줄입니다.
    
    2번째 줄입니다.
    
    3번째 줄입니다.
    
    4번째 줄입니다.
    
    5번째 줄입니다.
    
    6번째 줄입니다.
    
    7번째 줄입니다.
    
    8번째 줄입니다.
    
    9번째 줄입니다.
    
    10번째 줄입니다.
    


##### 3. `read()`
- `read()`는 파일의 내용 전체를 문자열로 돌려준다.


```python
f = open('/Users/castle1/Posts/python/test.txt','r')
data = f.read()
print(data)
f.close()
```

    1번째 줄입니다.
    2번째 줄입니다.
    3번째 줄입니다.
    4번째 줄입니다.
    5번째 줄입니다.
    6번째 줄입니다.
    7번째 줄입니다.
    8번째 줄입니다.
    9번째 줄입니다.
    10번째 줄입니다.
    


### 파일에 새로운 내용 추가하기

- `쓰기모드(w)`로 파일을 열 때 이미 존재하는 파일이면 내용이 모두 사라지게 된다.
- 원래 있던 값을 유지하면서 새로운 값을 추가할 경우가 발생할 수 있다.
- `추가모드(a)`를 사용한다.


```python
f = open('/Users/castle1/Posts/python/test.txt','a')
for i in range(11,20):
    data = '%d번째 줄입니다.\n' %i
    f.write(data)
f.close()
```

![a모드](/assets/images/git_github_img/a모드.png)

### `with문`

- 항상 close()하는것이 좋다.
- 하지만 `with`는 이를 자동화할 수 있다.
- `with블록`을 벗어나는 순간 열린 파일 객체 f가 자동으로 close되어 편리하다.


```python
with open('foo.txt','w') as f:
    f.write('python is funny')
```

###  `sys모듈`로 매개변수 주기

>ex)
>>(base) castle1@wsi python % cat test.txt

- windows 환경에서는 type
- macOS 환경에서는 cat
- cat(type) 명령어는 바로 뒤에 적힌 파일 이름을 인수로 받아 그내용을 출력해주는 프롬프트 명령어
- 대부분의 명령 프롬프트 명령어는 명령행에서 매개변수를 직접 주어 프러그램을 실행하는 방식을 따른다.
- 이러한 기능을 파이썬에도 적용 가능하다.

>`sys모듈`을 사용하여 매개변수르 직접 줄 수 있다.
>>`sys모듈`을 사용하려면 `sys`를 `import`해야한다. ex) import sys


```python
import sys

f = open('/Users/castle1/Desktop/sys.py','w')
args = sys.argv[1:]
for i in args:
    print(i)
```

- 이력받은 인수를 for문을 통해 차례대로 출력
- sys모듈의 argv는 명령 창에서 입력한 인수를 의미
- aaa,bbb,ccc를 입력했다면 argv[0] -> 파일 일름 sys.py, argv[1] -> aaa, argv[2] -> bbb, argv[3] -> ccc

<P style ="vertical-align: bottom; text-align: right;">출처:점프 투 파이썬</p>
