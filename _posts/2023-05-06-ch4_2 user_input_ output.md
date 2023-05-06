---
layout: single
title:  "ch4-2. 사용자 입력과 출력"
categories : python
---
# 사용자 입력과 출력

### 사용자 입력

>사용자가 입력한 값을 변수에 대입
>>input() 함수사용


```python
a = input()
```

    python is funny



```python
a
```




    'python is funny'



 - inupt()은 입려되는 모든 것을 `문자열`로 취급
 
 ### 프롬프트 값을 띄워서 사용자 입력받기
 
 - input() 괄호안에 질문을 입력하여 프롬프트를 띄워준다.


```python
num = input('숫자를 입력하세요 : ')
print(num)
```

    숫자를 입력하세요 : 3
    3


### print() 알아보기


```python
a = 123 # 숫자
print(a)

a= 'python' #문자열
print(a)

a = [1,2,3] # 리스트
print(a)
```

    123
    python
    [1, 2, 3]


### 따옴표 `''`,`""`로 둘러싸인 문자열은 `+` 연산과 동일 


```python
print("python""is""funny")
print("python"+"is"+"funny")

```

    pythonisfunny
    pythonisfunny


### 문자열 띄어쓰기는 `콤마(,)`로 한다


```python
print('python', 'is', 'funny')
```

    python is funny


### 한줄에 결괏값 출력하기

- `end`를 사용


```python
for i in range(10):
    print(i,end=' ')
    
```

    0 1 2 3 4 5 6 7 8 9 

<P style ="vertical-align: bottom; text-align: right;">출처:점프 투 파이썬</p>
