---
layout: single
title:  "파이썬 포스팅 테스트"
---
<!DOCTYPE html>
<head>
  <title>테스트</title>
</head>
<html>

    <body>
        <h1>파이썬이란?</h1>
        <hr>
        <img src ="https://blog.kakaocdn.net/dn/bkb4o9/btqIs89bNMJ/XkDr4WGfBBbQANYDLgxr31/img.jpg" style="float:left; clear:both; width:450px; height:300px;"/>
        <div style="clear:both; margin-bottom:20px"></div><p style="font-size:18px; line-height:lem">파이썬은 1990년 암스트레담의 귀도 반 로섬(Guido Van Rossum)이 개발한 인터프리터 언어이다. 자신이 좋아하는 코미디 쇼인 '몬티 파이썬의 날아다니는 서커스'에서 따왔다고 한다.<br>파이썬은 컴퓨터 프로그래밍 교육을 위해 많이 사용하는 언어이다. 또한 파이썬 프로그래밍은 <u>공동작업과 유지보수가 매우 쉽고 편리하다.</u><br></p>
        <br>
        <h2>파이썬의 특징</h2>
            <ul>
                <li>파이썬은 인간다운 언어</li>  
                <li>파이썬은 문법이 쉬워 빠르게 배울 수 있다.</li>
                <li>파이썬은 무료지만 강력하다.</li>
                <li>파이썬은 간결하다.</li>
                <li>파이썬은 개발속도가 빠르다.</li>
             </ul>
        <h2>파이썬으로 무엇을 할 수 있을까?</h2>
            <ul>
                <li>시스템 유틸리티 제작</li> 
                <li>GUI프로그래밍</li>
                <li>C/C++와의 결합</li>
                <li>웹 프로그래밍</li>
                <li>수치 연산 프로그래밍</li>
                <li>데이터베이스 프로그래밍</li>
                <li>데이터 분석, 사물 인터넷</li>
            </ul>
        <h2>파이썬으로 할 수 없는일</h2>
            <ul>
                <li>시스템과 밀접한 프로그래밍 영역</li>
                <li>모바일 프로그래밍</li>
            </ul>
        <h2>파이썬 기초 문법</h2>
            <ul>
                <li>사칙연산</li>
            </ul>
    </body>
</html>


```python
1+2
```




    3



<ul>
   <li>나눗셈과 곱셈</li> 
</ul>


```python
3 / 2.4
```




    1.25




```python
3 * 9
```




    27



<ul>
   <li>변수애 문자 대입하고 계산하기</li> 
</ul>


```python
a = 1
b = 2
a + b
```




    3




```python
a = 'python'
a
```




    'python'




```python
a = 'python'
print(a)
```

    python


<ul>
   <li>조건문 if</li> 
</ul>


```python
a = 3
if a > 1: # 만약 a가 1보다 크다면 print 출력
    print('a is greater than 1')
```

    a is greater than 1


<ul>
   <li>반목문</li> 
</ul>


```python
for a in [1,2,3]: #리스트 [1,2,3] 앞에서부터 하나씩 변수a에 대입후 print 수행
    print(a)
```

    1
    2
    3


<ul>
   <li>반목문 while</li> 
</ul>


```python
i = 0
while i< 3: #i기 3보다 작을때까지 계속 반복
    i = i+1 #i기 3보다 작은수였다면 i변수에 있는 값에 1을 더한후 다시 i에 대입 즉, i의 값을 1씩 더한다는 의미, i가 4가되면 반복하지 않는다.
    print(i)
```

    1
    2
    3


<ul>
   <li>함수</li> 
</ul>


```python
def add(a,b): #add 라는 함수생성 add 함수가 호출되면 add 함수의 각파라미터를 더해서 return
    return a+b
add(3,4)
```




    7



<P style ="vertical-align: bottom; text-align: right;">출처:점프 투 파이썬</p>
