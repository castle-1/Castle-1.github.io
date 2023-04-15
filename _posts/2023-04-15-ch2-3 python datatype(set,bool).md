---
layout: single
title:  "ch2-3. 파이썬데이터 타입(set, bool)"
categories : python
---
# 집합 자료형
- 집함에 관련된 것을 쉽게 처리하기위한 자료형
- set은 중복을 허용하지 않는다.
- set은 순서가 없다.
>set()


```python
s1 = set([1,2,3])
s1
```




    {1, 2, 3}




```python
s2 = set('hello')
s2
```




    {'e', 'h', 'l', 'o'}



- set은 자료형 순서가 없기때문에 인덱싱으로 값을 얻을 수 없다.
- set 자료형에 저장된 값을 인덱싱으로 접근하려면 리스트 또는 튜플로 변환후 접근해야한다.


```python
s1 = set([1,2,3])
l1 = list(s1) # 리스트로 변환
l1
```




    [1, 2, 3]




```python
t1 = tuple(s1) #튜플로 변환
t1
```




    (1, 2, 3)



### 교집합, 합집합, 차집합 구하기

1. 교집합(&,intersection()) 


```python
s1 = set([1,2,3,4,5,6])
s2 = set([4,5,6,7,8,9])

s1 & s2
```




    {4, 5, 6}




```python
s1.intersection(s2) #동일한 표현
s2.intersection(s1)
```




    {4, 5, 6}



2. 합집합(|, union()) 


```python
s1 | s2
```




    {1, 2, 3, 4, 5, 6, 7, 8, 9}




```python
s1.union(s2)
s2.union(s1)
```




    {1, 2, 3, 4, 5, 6, 7, 8, 9}



3. 차집합(-,difference())


```python
s1 - s2
```




    {1, 2, 3}




```python
s2 - s1
```




    {7, 8, 9}




```python
s1.difference(s2)
```




    {1, 2, 3}




```python
s2.difference(s1)
```




    {7, 8, 9}



### 집합 자료형 관련 함수

1. 값 1개 추가하기(add)


```python
s1 = set([1,2,3])
s1.add(4)
s1
```




    {1, 2, 3, 4}



2. 값 여러개 추가하기(update)


```python
s1 = set([1,2,3])
s1.update([4,5,6])
s1
```




    {1, 2, 3, 4, 5, 6}



3. 특정값 제거하기(remove)


```python
s1 = set([1,2,3])
s1.remove(2)
s1
```




    {1, 3}



# 불 자료형

- 불 자료형이란 참과 거짓을 나타내는 자료형


```python
a = True
b = False

print(type(a))
print(type(b))
```

    <class 'bool'>
    <class 'bool'>


- 불 자료형은 조건문의 반환 값으로도 사용.


```python
1 == 1
```




    True




```python
2 > 1
```




    True




```python
2 < 1
```




    False



### 자료형의 참과 거짓<br>
>문자열
>>"python" -> 참<br> "" ->거짓
<hr>

>리스트
>>[1,2,3] -> 참<br> [] -> 거짓
<hr>

>튜플
>>() -> 거짓
<hr>

>딕셔너리
>>{} -> 거짓
<hr>

>숫자형
>>0이 아닌숫자 -> 참<br> 0 -> 거짓
<hr>

>
>>none -> 거짓
<hr>

- 문자열, 리스트, 튜플, 딕셔너리 등의 값이 비어있으면 거짓
- 비어있지 않으면 참
- none 는 거짓을 뜻한다.


```python
if []: # 비어있는 리스트는 거짓
    print("true")
else:
    print("flase")
```

    flase



```python
if [1,2,3]: # 즉, [1,2,3]이 참이면 true 출력 그렇지 않다면 false출력
    print("true")
else:
    print("flase")
```

    true


### 불연산


```python
bool('python')
```




    True




```python
bool('') #문자열이 비어있기 때문에 false
```




    False




```python
bool([1,2,3])
```




    True




```python
bool([])
```




    False




```python
bool(0) #숫자 0은 false
```




    False




```python
bool(3)
```




    True

<P style ="vertical-align: bottom; text-align: right;">출처:점프 투 파이썬</p>
