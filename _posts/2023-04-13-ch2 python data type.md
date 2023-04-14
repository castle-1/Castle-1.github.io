---
layout: single
title:  "ch2. 파이썬데이터 타입(숫자형,문자열)"
categories : python
---

<h1>1. 숫자형</h1>
<hr>
  <ul>
      <li>숫자형이란 숫자 형태로 이루어진 자료형</li>
      <li>정수, 실수, 8진수, 16진수</li>
  </ul>

<h3>숫자형 사용하기</h3>
  <ul>
      <li>정수형 : 정수를 뜻하는 자료형</li>
      <li>양의 정수</li>
      <li>음의 정수</li>
  </ul>


```python
a = 123
b = -123
print(a) # 양의 정수
print(b) # 음의정수
```

    123
    -123


<ul>
    <li>실수형 : 소수점이 포함된 숫자</li>
</ul>


```python
a = 1.234
print(a)
```

    1.234


<ul>
    <li>컴퓨터식 지수 표현방식</li>
</ul>


```python
a = 4.23E10 #(e,E 둘다 표현가능), 4.23E10 -> 4.24 * 10의10제곱
b = 4.24e-10 # 4.24e-10 -> 4.24 * 10의-10제곱 
print(a)
print(b)
```

    42300000000.0
    4.24e-10


<ul>
    <li>8진수 : 0o(숫자0 + 알파벳 o)으로 시작하여 표현</li>
</ul>


```python
a = 0o0177
print(a)
```

    127


<ul>
    <li>16진수 : 0x 로 시작하여 표현</li>
</ul>


```python
a = 0x3af
b = 0xABC
print(a)
print(b)
```

    943
    2748


<h3>숫자형 연산하기</h3>
  <ul>
      <li>사칙연산</li>
  </ul>


```python
a = 7
b = 3
print(a+b)
print(a*b)
print(a/b)
```

    10
    21
    2.3333333333333335


<ul>
    <li>제곱 연산자(**)</li>
</ul>


```python
a = 7
b = 9
print(a**b) # 7의9제곱
```

    40353607


<ul>
    <li>나눗셈 후 나머지 반환하는 연산자(%)</li>
</ul>


```python
a = 7
b = 3
print(a%b)
```

    1


<ul>
    <li>나눗셈 후 몫을 반환하는 연산자(//)</li>
</ul>


```python
a = 7
b = 3
print(a/b)
print(a//b)
```

    2.3333333333333335
    2


<h1>2. 문자열</h1>
<hr>
  <ul>
      <li>문자열이란 문자, 단어 등으로 구성된 문자드의 집합</li>
      <li>"you need python"</li>
      <li>"파이썬"</li>
      <li>"a"</li>
      <li>"123"</li>
  </ul>

<h3>문자열 만들고 사용하기</h3>
  <ul>
      <li>문자열 선언하기</li>
  </ul>


```python
a = "hello world!"
b = 'hello world!'
c = """hello world!"""
d = '''hello world!'''
print(a)
print(b)
print(c)
print(d)
```

    hello world!
    hello world!
    hello world!
    hello world!



```python
a = "python's funny" #문자열 안에 작은따옴표(') 포함하기 작은따옴표를 포함하면 문자열을 큰따옴표("")로 감싸야한다.
print(a)
b = '"python is easy"'#문자열 안에 큰따옴표를 포함했으면 문자열을 작은따옴표로 감싸야한다.
print(b)
d = 'python\'s funny' #백슬래시(\)를 사용해서 표현가능. '/' 뒤에 ', "를 사용하면 문자열을 둘러싸는 "기호"의 의미가 아니라 문자 자체를뜻한다. 
print(d)
```

    python's funny
    "python is easy"
    python's funny


<ul>
    <li>줄을 바꿔주는 이스케이프 코드 '\n'</li>
</ul>


```python
a = 'python is very\n funny' #veery 뒤에서 개행
print(a)

#작은따옴표(''') 대신 큰따옴표(""")도 사용가능
b = ''' 
    python is very funny
    python is very very funny
    '''
print(b)
```

    python is very
     funny
     
        python is very funny
        python is very very funny
        


<h3>문자열 연산하기</h3>
  <ul>
      <li>파이썬에서는 문자열을 더하거나 곱할 수 있다.</li>
      <li>문자열 더해서 연결하기</li>
  </ul>


```python
a = "python is"
b = " funny"
print(a+b)#a의 문자열과 b의 문자열을 연결해서 출력
```

    python is funny


<ul>
    <li>문자열 곱하기</li>
</ul>


```python
a = "python" #a의 문자열 3번 연속으로 출력
print(a*3)

print("="*10)
print(a)
print("="*10)
```

    pythonpythonpython
    ==========
    python
    ==========


<ul>
  <li>문자열 길이 구하기</li>
  <li>len 함수 사용</li>
</ul>


```python
a = "python"
print(len(a))
len(a) #len함수 단독으로도 출력가능
```

    6





    6



<h3>문자열 인덱싱과 슬라이싱</h3>
  <ul>
    <li>인덱싱  : 인덱싱이란 무엇인가를 가리킨다는 의미</li>
    <li>슬라이싱 : 슬라이싱이란 무엇인가를 잘라낸다는 의미 </li>
  </ul>


```python
#인덱싱 
a = "python is funny"
print(a[4]) #a변수의 4번 인덱스,파이썬은 0부터 센다. 공백도 포함
            #인덱싱은 문자열 안의 특정한 값을 뽑아내는 역할을 한다.
print("-"*20)

print(a[0])
print(a[-0]) # 숫자 0과 -0은 같은의미 따라서 a[0] = a[-0]
print("-"*20)

print(a[-1]) # '-'가 붙어있으면 문자열을 뒤에서부터 센다.
print(a[-3]) # 뒤에서 3번째
```

    o
    --------------------
    p
    p
    --------------------
    y
    n



```python
#슬라이싱
a = "python is funny"
b = a[0] + a[5] + a[10] #0, 5, 10번 인덱스의 문자를 연결해서 출력
print(b)
print("-"*20)

c = a[0:5] #슬라이싱 기법 a[0:5] ->a[시작번호:끝번호] 끝번호 앞까지 출력(끝 번호는 해당하지 않아 출력되지 않는다.)
print(c)
d = a[0:6]
print(d)
e = a[0:8] # !주의 공백문자도 포함
print(e)
print("-"*20)

f = a[1:3]
print(f) #시[번호가 0일 필요는 없다.
print(a[7:]) #끝번호르 생략하면 끝가지 출력 a[7:] ->7번 인덱스부터 마지막인덱스까지
print(a[:7]) # 시작번호를 생략하면 처음부터 지정한 인덱스까지 출력 a[:7] -> 처음 인덱스부터 7번 앞 인덱스까지 출력
print("-"*20)

print(a[3:-3])# '-'기호 사용가능 a[3:-3] -> 3번 인덱스부터 뒤에서 3번까 인덱스까지
```

    pnf
    --------------------
    pytho
    python
    python i
    --------------------
    yt
    is funny
    python 
    --------------------
    hon is fu


<ul>
    <li>슬라이싱으로 문자열 나누기</li>
</ul>


```python
a = "20230408Rainy"
date = a[:8]
weathaer = a[8:]
print(date) #날짜와 날씨로 나누기
print(weathaer)
print("-"*20)
      
year = a[:4] #날짜에서 년, 월, 일로 나누기
month = a[4:6]
day = a[6:8]
print(year)
print(month)
print(day)      
```

    20230408
    Rainy
    --------------------
    2023
    04
    08


<h3>문자열 포매팅</h3>
  <ul>
    <li>문자열 안의 특정한 값을 바꿔야 할 경우에 사용</li>
    <li>문자열 안에 어떤 값을 삽임하는 방법</li>
  </ul>


```python
#숫자 대입
a = "i eat %d apples" %3 
print(a)
```

    i eat 3 apples



```python
#문자열 대입
a = "i eat %s apples" %"five"
print(a)
```

    i eat five apples



```python
#숫자 값을 나타내는 변수로 대입
num = 3
a = "i eat %d apples" %num
print(a)
```

    i eat 3 apples



```python
#2개 이상의 값 넣기
num = 3
day = "five"
a = "i ate %d apples. so i was sick for %s days." %(num,day)
print(a)
```

    i ate 3 apples. so i was sick for five days.


<ul>
  <li>문자열 포맷 코드</li>
</ul>

<table align = "left">
  <th>코드</th>
  <th>설명</th>
  <tr>
    <td>%s</td>
    <td>문자열</td>
  </tr>
  <tr>
    <td>%c</td>
    <td>문자1개</td>
  </tr>
  <tr>
    <td>%d</td>
    <td>정수</td>
  </tr>
  <tr>
    <td>%f</td>
    <td>부동소수</td>
  </tr>
  <tr>
    <td>%o</td>
    <td>8진수</td>
  </tr>
  <tr>
    <td>%x</td>
    <td>16진수</td>
  </tr>
  <tr>
    <td>%%</td>
    <td>literal %(%자체를 표현하고 싶을때)</td>
  </tr>
</table>

<h3>포맷 코드와 숫자 함께 사용하기</h3>
    
<ul>
  <li>정렬과 공백</li>
</ul>


```python
a = "%10s" % "hi" #%10s ->전체 길이가 10개인 문자열 공간, 대입되는 값을 오른쪽 정렬하고 나머지는 공백으로
print(a)
```

            hi


<table border = "2" align="left">
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>h</th>
  <th>i</th>
</table>


```python
a = "%-10sjane" % "hi" #-%10s -> 전체 길이가 10개인 문자열 공간, 대입되는 값을 왼쪽정렬하고 나머지는 공백
                       #즉, 젠체 길이가 10개인 문자열에서 hi를 왼쪽정렬후 jane를 출력
print(a)
```

    hi        jane


<table border = "2" align="left">
  <th>h</th>
  <th>i</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>j</th>
  <th>a</th>
  <th>n</th>
  <th>e</th>
</table>

<ul>
    <li>소수점 표현</li>
</ul>


```python
a = "%0.4f" % 3.1415926535897932384626433 # 소수 4번째 자리까지 출력 즉 '.'의 의미는 소수점 포인트, 뒤의 숫자4는 소수점 뒤에나올 숫자 개수
print(a)
```

    3.1416



```python
a = "%10.4f" % 3.1415926535897932384626433 #10개인 문자열에 소수점 4번째 자리까지 표현후 공백
print(a)
```

        3.1416


<table border = "2" align="left">
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>*</th>
  <th>3</th>
  <th>.</th>
  <th>1</th>
  <th>4</th>
  <th>1</th>
  <th>6</th>
</table>

<h3>format 함수를 사용한 포매팅</h3>


```python
#숫자 바로 대입하기
a = "i eat {0} apples".format(3)
print(a)
```

    i eat 3 apples



```python
#문자열 바로 대입하기
a = "i eat {0} apples".format("five")
print(a)
```

    i eat five apples



```python
#숫자 값을 가진 변수로 대입하기
num = 3
a = "i eat {0} apples".format(num)
print(a)
```

    i eat 3 apples



```python
#2개 이상의 값 넣기
num = 3
day = "five"
a = "i ate {0} apples. so i was sick for {1} days".format(num,day)
print(a)
```

    i ate 3 apples. so i was sick for five days



```python
#이름으로 넣기
a = "i ate {num} apples. so i was sick for {day} days".format(num=3,day=5)
print(a)
```

    i ate 3 apples. so i was sick for 5 days



```python
#인덱스와 이름을 혼용해서넣기
a = "i ate {0} apples. so i was sick for {day} days".format(10,day = 5)
print(a)
```

    i ate 10 apples. so i was sick for 5 days


<ul>
  <li>정렬</li>
</ul>


```python
#오른쪽 정렬(:>)
a = "{0:>10}".format("hi") #화살표 뱡향에 따라 정령이 달라진다.
print(a)
#왼쪽 정렬(:<)
b = "{0:<10}".format("hi")
print(b)
```

            hi
    hi        



```python
#가운데 정렬(:^)
a = "{0:^10}".format("hi")
print(a)
```

        hi    



```python
#공백 채우기
a = "{0:=^10}".format("hi")
print(a)
b = "{0:!<10}".format("hi")
print(b)
```

    ====hi====
    hi!!!!!!!!


<ul>
  <li>소수점 표현하기</li>
</ul>


```python
#소수점 4자리 표현 ->0.4f 와 동일한 표현
y = 3.141592
a = "{0:0.4f}".format(y)
print(a)

#자리수를 10으로 맞추기 10.4f와 같은표현
b = "{0:10.4f}".format(y)
print(b)
```

    3.1416
        3.1416


<ul>
  <li>{ 또는 } 표현하기</li>
</ul>


```python
a = "{{and}}".format()
print(a)
```

    {and}


<ul>
  <li>f 문자열 포매팅</li>
  <li>문자열 앞에 f접두사를 붙이면 f문자열 포매팅이 가능</li>
  <li>f문자열 포매팅은 변수 값을 생성후 그 값을 참조할 수 있다.</li>
  <li>f문자열은 표현식을 지원한다.</li>
</ul>


```python
name = "고길동"
age = 40
print(f"내 이름은 {name}이다. 나이는{age}살이다.")

#f문자열 표현식 지원
print(f"나는 내년이면 {age+1}살이 된다.")

#딕셔너리 문자열 포매팅
a = {"name2" : "둘리", "age2" : 20}
print(f"내이름은 {a['name2']}. 빙하타고왔지 나이는{a['age2']}살이다.")
```

    내 이름은 고길동이다. 나이는40살이다.
    나는 내년이면 41살이 된다.
    내이름은 둘리. 빙하타고왔지 나이는20살이다.


<ul>
  <li>정렬</li>
</ul>


```python
#왼쪽 정렬
left = f"{'hi':<10}"
print(left)

#오른쪽 정렬
right = f"{'hi':>10}"
print(right)

#가운데 정렬
center = f"{'hi':^10}"
print(center)
```

    hi        
            hi
        hi    


<ul>
  <li>공백 채우기</li>
</ul>


```python
a = f"{'hi':=^10}"
print(a)

b = f"{'hi':!<10}"
print(b)
```

    ====hi====
    hi!!!!!!!!


<ul>
    <li>소수점 표현하기</li>
</ul>


```python
#소수 4째자리까지 표현
a = 3.141592
print(f"{a:0.4f}")

#소수 4째자리까지 표햔하고 총 자리수는 10자리
print(f"{a:10.4f}")
```

    3.1416
        3.1416


<h3>문자열 관련 함수</h3>
<ul>
  <li>문자열은 자체적으로 함수를 가지고 있다. -> 문자열 내장함수라고 한다.</li>
  <li>함수르 사용하려면 문자열 변수 뒤에 '.'을 쓰고 함수이름을 쓰면 사용가능하다.</li>
</ul>


```python
#문자 개수 세기(count)
a = "apple"
print(a.count('p')) # a의 문자열 즉, apple 문자열에서 p의 개수를 돌려준다.
```

    2



```python
#위치 알려주기(find) - 문자열중 처음 나온 위치를 반환 만약 찾는 문자열이 없다면 -1을 반환
a = "python is funny"
print(a.find("p"))
print(a.find("n"))
print(a.find("x"))
```

    0
    5
    -1



```python
#위치 알려주기(index) - 문자열중 처음 나온 위치를 반환 만약 찾는 문자열이 없다면 오류발생
a = "python is funny"
print(a.index("p"))
print(a.index("x")) #x가 없기때문에 오류 발생
```

    0



    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[30], line 4
          2 a = "python is funny"
          3 print(a.index("p"))
    ----> 4 print(a.index("x"))


    ValueError: substring not found



```python
#문자열 삽입
print(",".join("abcd")) # abcd 문자열 사이사이에 ',' 삽입
```

    a,b,c,d


>join
>>문자열 뿐만 아니라 리스트, 튜플도 입력으로 사용할 수 있다.


```python
#join 함수의 입력으로 리스트 사용
print(",".join(["a","b","c","d"]))
```

    a,b,c,d



```python
#소문자 -> 대문자 (upper)
a = "hi"
print(a.upper())

#대문자 -> 소문자 (lower)
b = "HI"
print(b.lower())
```

    HI
    hi



```python
#왼쪽 공백 지우기(lstrip) - 문자열중 왼쪽에 한 칸 이상의 연속된 공백을 모두 지운다. lstrip 에서 l은 left를 의미
a = " hi " #hi양 옆으로 공백 한칸씩
b = "hi"
print(a.lstrip())
print(b)
```

    hi 
    hi



```python
#오른쪽 공백 지우기(rstrip) - 문자열중 가장 오른쪽에 있는 한 칸 이상의 연속된 공백을 모두 지운다. rstrip 에서 r은 right를 의미
a = " hi "
b = "hi"

print(a.rstrip())
print(b)
```

     hi
    hi



```python
#양쪽 공백 지우기(strip) - 문자열 양쪽에 있는 한 칸 이상의 연속된 공백을 모두 지운다.
a = " hi "
b = "hi"

print(a.strip())
print(b)
```

    hi
    hi



```python
#문자여 바꾸기(replace) -> replace("바뀌게될 문자","바꿀문자")
a = "python is funny"
print(a.replace("python", "java"))
```

    java is funny



```python
#문자열 나누기(split)
a = "python is funny"
print(a.split()) # 공백을 기준으로 문자열을 나누고 리스트에 들어간다.

b = "a:b:c:d"
print(b.split(":")) # :을 기준으로 문자열을 나누고 리스트에 들어간다.
```

    ['python', 'is', 'funny']
    ['a', 'b', 'c', 'd']



```python

```
<P style ="vertical-align: bottom; text-align: right;">출처:점프 투 파이썬</p>
