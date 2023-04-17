# if 문 

- 주어진 조건을 판단후 그상황에 맞게 처리해야 하는 경우가 발생.
- 조건을 판단하여 해당 조건에 맞는 상황을 수행하는데 쓰인다.
- 조건문이 참이면 if문 바로다음 문장을수행, 거짓이면 else문을 수행한다.
- !주의 if문을 만들때는 if 조건문: 바로아래 문장 부터 if문에 속하는 모든 문장에는 들여쓰기를 해야한다.
<br>

>if문 기본 구조
>>if 조건문:<br>
    <blockquote>수행할문장1</blockquote><br>
    <blockquote>수행할문장2</blockquote><br>
    <blockquote>...</blockquote><br>
  else:<br>
    <blockquote>수행할문장1</blockquote><br>
    <blockquote>수행할문장2</blockquote><br>
    <blockquote>...</blockquote><br>
    
### 조건문이란?
- '조건문'이란 참과 거짓을 판단하는 문장

#### 비교연산자

- t < y : y가 t보다 크다.
- t > y : t가 y보다 크다.
- t == y : t와 y가 같다.
- t != y : t와 y가 같지않다.
- t >= y : t가 y보다 크거나 같다.
- t <= y : y가 t보다 크거나 같다.




```python
a = 1
b = 2
print(a>b)
print(a<b)
```

    False
    True


#### 논리연산자 and, or, not

- x or y : x또는 y 둘중 하나만 참이면 참
- x and y : x,y 모두 참이여야 참
- not x : x가 거짓이면 참

#### x in s , x not in s(in -> ~안에)

- x in 리스트
- x in 튜플
- x in 문자열
<br>
    
- x not in 리스트
- x not in 튜플
- x not in 문자열


```python
#리스트
1 in [1,2,3 # 1이 리스트 안에 있는가?
```




    True




```python
#리스트
1 not in [1,2,3] # 1이 리스트 않에 없는가?
```




    False




```python
#튜플
'a' in ('a','b','c')
```




    True




```python
#튜플
'j' not in('a','b','c')
```




    True



#### pass
- 아무런 일도 하지 않도록 설정
>표현법
>>poket = ['paper','money']<br>
  if 'money' in poket:<br>
      <blockquote>pass</blockquote><br>
  else:<br>
      <blockquote>print('돈을 지불해라')</blockquote><br>

### 다양한 조건을 판단하는 elif 
- if와 else 만으로 다양한 조건을 판단하기 어려운 경우가 존재한다.
- 다중 조건 판단을 가능하게하는 elif를 사용.
- 즉, elif는 이전 조건문이 거짓일때 수행된다.
>표현법
>>poket = ['paper', 'cellphone']<br>
if 'money' in poket:<br><blockquote>print('택시를 타고가라')</blockquote><br>
elif card: <br><blockquote>print('택시를 타고가라')</blockquote><br>
else:<br><blockquote>print('걸어가라')</blockquote>

### 조건부 표현식
- 조건부 표현식은 가독성에 유리, 한줄로 작성할 수 있어 활용성이 높다.


```python
# if score >= 60:
#     message = "success"
# else:
#     message = "fail"
# 위코드를 간결하게 표현가능
score = 70
message = "success" if score >= 60 else "fail"
print(score)
```

    70

