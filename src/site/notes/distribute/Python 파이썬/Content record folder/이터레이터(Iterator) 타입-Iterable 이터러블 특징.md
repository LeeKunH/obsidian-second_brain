---
{"dg-publish":true,"permalink":"/distribute/python/content-record-folder/iterator-iterable/","tags":["파이썬"],"noteIcon":""}
---

### 날짜 2023-10-13 13:08

### 주제-키워드 =>



---
### 연관된 기록 =>
위에서 작성한 내용과 연관성이 있는 기록-노트를 연결.
" [[]] "
- [[distribute/Python 파이썬/Content record folder/제너레이터-지연평가구현체-컴프리헨션-yield\|제너레이터-지연평가구현체-컴프리헨션-yield]]




-------------------------------
- ### 3회 기록/영구노트 기록 단계 =>
	ㅡ 이 기록을 왜 시작하게 되었는지 생각.
	ㅡ 폴더를 생성하고 목차에 작은 기록들을 연결시킨다.
		ㅡ 2회 기록단계에서 기록한 키워드 요약들을 연결시킨다

ㅡ 이터레이터-iterator
순서대로 다음 값을 리턴할 수 있는 객체 의미.
	+ 객체 = 파이썬 데이터 타입
	
이터레이터는 `__iter__()` 메서드와 `__next__()` 메서드를 구현한 객체로, `__iter__()` 메서드는 이터레이터 객체 자신을 반환하고 `__next__()` 메서드는 다음 값을 반환
	ㅡ
	따라서 다음 값을 리턴할 수 있었던 이유는 자체적으로 이미 가지고 있는 `__next__`메서드를 통해 다음 값을 가져오게 되는 것.


ㅡ "iterable-이터러블 하다"
	= 내부 요소(member 멤버)를 하나씩 리턴할 수 있는 특징을 가진 객체 = (내부에 `__iter__` 존재하면 이터러블한 객체임) 하지만 아직은? 스스로 반환할 수 x 
	.
	= `__next__` 메서드 존재 x  = 스스로? 다음 값을 반환할 수 없다.
		이 메서드가 존재하면 이터레이터 객체임
	.
	= 여러 요소를 순회할 수 있는 객체
	
ex) 리스트는 이터러블한 특징을 가진 객체이지만 직접적인 이터레이터 객체는 아님. 그러나 `for` 루프와 같은 반복 구문을 사용하면 리스트를 순회하면서 이터레이터 객체를 *내부적으로 생성* > 이 이터레이터 객체가 리스트의 항목을 하나씩 반환하며, 이런 동작으로 리스트를 반복 가능하게 만듬. 
따라서 `for` 루프는 이터레이터 객체를 생성(반환)하고 사용하는 것과 같은 역할을 하는 것.
	
```
a = [1, 2, 3] 
print(a.__next__) # AttributeError 발생
```
	
> [!NOTE]
> 즉 다시 요약하면 for반복문과 이터러블한 특징을 가진 리스트를 사용하면
> 	내부적으로 iter특수 메서드 호출/실행
> 		리스트 객체 > 이터레이터 객체됨.
> 			그리고 for문 시행이 될 떄마다 next 특수 메서드가 호출되어 1개씩 반환/출력되는 것.

ㅡ
즉, 이터러블한 특징을 가지고 있는 객체만이 이터레이터 타입이 될 수 있음.
	= 이터레이터는 이터러블한 객체에서 생성되며, 이터러블한 객체란 순회 가능한(iterable) 특징을 가진 객체를 의미합니다.
.
ㅡ "순회 가능한 객체" = "순서가 있는 객체" = "인덱스가 있는 객체"
는 모두 유사한 의미로 사용됨.
.
이러한 객체들은 순서대로 항목에 접근할 수 있는 특징을 가지며, 각 항목은 고유한 위치 또는 인덱스를 가지고 있음.
.
파이썬에서는 이러한 객체를 순회 가능한(iterable) 객체로 통칭하며, 이들을 반복(iterate)하거나 순환(loop)하면서 각 항목에 접근할 수 있음.
	.
이러한 객체들을 `for` 루프나 이터레이터를 사용하여 처리할 수 있으며, 인덱스가 있는 경우에는 특정 위치의 항목에 직접 접근할 수 있음.
	
ㅡ 참고자료 : [[distribute/Python 파이썬/Content record folder/05장 파이썬 날개 달기/05-5 내장 함수#ㅡ zip()\|05-5 내장 함수#ㅡ zip()]]
: 이터러블 객체에 들어있는 데이터를 확인하기 위해선 접근해야함.
어떻게?
변환 or 순회

-----------------
- ### 2회 기록/참고노트/복습-목차요약 단계 =>
	1회독 기록 노트 기반
	복습 및 키워드 요약 단계

- 이터레이터 - iterator
	- "다음 값을 리턴할 수 있는 객체"
	- `__iter__()` 메서드
	- `__next__()` 메서드
- iterable-이터러블
	- "내부 요소(member 멤버)를 하나씩 리턴할 수 있는 특징을 가진 객체" = "여러 요소를 순회할 수 있는 객체"
		- "순회 가능한 객체" = "순서가 있는 객체" = "인덱스가 있는 객체"
		- 특징만 가지고 있을 뿐 스스로 다음 값을 반환할 수 없기 때문에 아직 이터레이터 객체 x
			- ex) 리스트는 이터러블한 객체이지만 이터레이터 객체는 아님


---
- ### 1회독 기록/임시노트/본문 내용 =>
	전체적인 내용 기록



## Metadata
- Author: 티베트 모래여우
- Category: article
- URL: https://tibetsandfox.tistory.com/27


# ㅡ 파이썬(python) - 이터레이터(Iterator)
Note: 제목
==이터레이터는 **순서대로 다음 값을 리턴할 수 있는 객체를 의미**==
	=>
	객체 = 파이썬 데이터 타입
	
==자체적으로 내장하고 있는 next 메소드를 통해 다음 값을 가져올 수 있==습니다.
	
'순서대로'라는 말 때문에 list, tuple과 같은 타입의 객체를 생각하셨을 수도 있는데, 이것과는 다릅니다.

- 이터러블(iterable) 타입/특징

ㅡ 이터러블 타입(특징) 가진 객체
	ㅡ 시퀀스 타입 + set 타입+ dic 타입
	ㅡ 컬렉션 타입

-----
### ㅡ 선행학습 : 컬렉션(Collection) 타입과 시퀀스(Sequence) 타입
Note: 제목

ㅡ 참고자료 : [[distribute/Python 파이썬/Content record folder/시퀀스-컬렉션-타입\|시퀀스-컬렉션-타입]]


----
### ㅡ Iterable VS Iterator

ㅡ
==여러 요소를 순회할 수 있는 객체==를 "이터러블(Iterable)"이라고 부르며, ==이터레이터(Iterator) 객체는 이러한 이터러블 객체에서 생성됩==니다. ==따라서 이터레이터는 이터러블한 특징을 가진 객체에서 파생된 것==이라고 이해할 수 있습니다.

ㅡ
==**내부 요소(member)를 하나씩 리턴할 수 있는 객체==를 보고 Iterable하다고 합니다.** 쉽게 생각하면 우리가 ==평소에 많이 사용하는 **for문**을 떠올리시면 됩==니다.

```python
_list = [1,2,3,4,5]

for i in _list:
    print(i)
```
결과=>
이렇게 ==**for문을 통해 순회할 수 있는 객체를 Iterable하다고 생각**==하시면 됩니다. 대표적으로 위에서 잠깐 설명한 ==**시퀀스 타입**과 **컬렉션 타입**의 객체==가 있습니다.

> [!NOTE]
> 	=>
> 	시퀀스 타입과 컬렉션 타입모두
> 	이터레이블한 특징을 가지고 있구나
> 	.
> 	특징과 데이터 타입과 헷갈리지 말자

ㅡ 그럼 ==Iterable한 것과 Iterator는 무슨 차이==가 있는걸까요?

> [!NOTE]
> 	=>
> 	전자는 특징이고
> 	후자는 데이터 타입이고

	
쉽게 말하자면 ==**Iterable한 것****은 `__next__` 메소드가** **존재하지 않고** **Iterator는 존재**한다==고 생각하시면 됩니다.

==즉 **__next__ 메소드로 다음 값을 반환할 수 있으면 Iterator, 없으면 Iterable한 객체**==입니다.

-----
### ㅡ Iterable 객체를 Iterator로?
Note: 제목
==주목할 점은, ​**Iterable한 객체를 Iterator로 만들 수 있다**는 점==
	.(정확히는 내부에 `__iter__`라는 메소드가 있는 객체)

```
a = [1, 2, 3] 
print(a.__next__) # AttributeError 발생
```
	
그냥 list 타입의 데이터는 __next__ 메소드가 없습니다. 따라서 에러가 발생

> [!NOTE]
> 	=> 
> 	즉 리스트 타입은 이터레이블한 특징은 있지만 이터레이터는 아직은 아니다.
	
```python
a = [1, 2, 3]

print(type(a)) # <class 'list'>
a = iter(a)
print(type(a)) # <class 'list_iterator'>
print(a.__next__()) # 첫 실행시 1 출력
```
결과=>
하지만 이렇게 ==iter함수를 이용해 Iterator로 만들어 줄 수 있==습니다.
	
Iterator로 바꾼 후에는 정상적으로 `__next__` 함수가 작동하는 것을 볼 수 있습니다.
	Note: 리스트 자료형안에 다양한 자료형들이 존재하는데..1개씩 접근 출력

```python
a = [1, 2, 3]
print(a)
=>
[1, 2, 3]

a = [1, 2, 3].__iter__()
print(type(a)) # list_iterator
print(a)
=>
<class 'list_iterator'>
<list_iterator object at 0x0000028F1F670340>

```

> [!NOTE]
> =>
> 	저 특수 메서드가 호출되면 형변환이 발생하나보네
> 	그래서 출력이 객체로 나옴
	
위 방법은 이렇게 직접 __iter__ 메소드를 호출해 Iterator로 만들어 줄 수도 있습니다.

------

```python
a = [1, 2, 3]

a = iter(a)
print(a.__next__()) # 1 출력
print(a.__next__()) # 2 출력
print(a.__next__()) # 3 출력
print(a.__next__()) # StopIteration Exception 발생
```
결과=>
```
1
2
3

---------------------------------------------------------------------------
StopIteration                             Traceback (most recent call last)
Cell In [6], line 7
      5 print(a.__next__()) # 2 출력
      6 print(a.__next__()) # 3 출력
----> 7 print(a.__next__())

StopIteration:
```
=>
저 `__next__` 메소드를 이용해서 값을 계속 꺼내다보면 마지막 값에 도달하게 되는데, 마지막 값을 꺼내고 나서 `__next__`메소드를 호출하면 ==StopIteration이라는 예외가 발생==

> [!NOTE]
> 	=>
> 	즉 더이상 넘어갈 값이 없으면
> 	오류 발생

-------
### ㅡ for문과 Iterator


ㅡ
눈치채신 분도 계시겠지만 ==파이썬의 for문은 내부적으로 Iterator를 생성하여 동작==합니다.(==`__iter__` 메소드 이용==)

> [!NOTE] 추가내용
> ㅡ
> 파이썬의 ==리스트(List)는 반복 가능한(iterable) 특징을 가지고 있는 객체==입니다.
> 	
> ==`for` 루프가== 리스트를 반복하면 ==내부적으로 리스트 객체에 `__iter__` 메서드가 호출==되어 ==이터레이터 객체를 반환==
> 	
> 이 ==이터레이터 객체는 `__next__` 메서드를 가지고 있어==서 ==요소에 순차적으로 접근==하면서 `for` 루프에서 ==출력할 수 있게 됩==
> 	
> 따라서 `for` 루프를 사용하면 객체의 요소를 하나씩 순회하면서 처리할 수 있었던 것.
> 	= 
> 	==`for` 루프를 사용하면 `__iter__`와 `__next__` 메서드를 직접 호출할 필요 없이 반복 가능한 객체의 요소에 접근할 수 있습니다.==
> 	=
> 	==`for` 루프를 사용하면== ==파이썬 인터프리터가== 반복 가능한==(iterable)특징을 가진 객체==(현재는 리스트)의 ==`__iter__` 메서드를 내부적으로 호출==하여 ==리스트 객체 > 이터레이터(iterator) 객체==를 얻는 것.
	
예를들어 리스트를 순회하는 for문이라 하면, **해당 리스트의 Iterator를 생성한 다음 __next__메소드를 이용해 순회를 도는 방식**입니다.
	
대충 그림으로 표현하자면 다음과 같습니다.

> [!NOTE]
> 	=>
> 	리스트 타입 객체 > for 반복문으로 인해 내부적으로 `__iter__`가 호출되어 > 잠시? 이터레이터 객체가 되서 시행될 때 마다 `__next__` 사용되고 있었던 것
> 	.
> 	즉 다시 요약하면
> 	for반복문과 이터러블한 특징을 가진 리스트를 사용하면
> 		내부적으로 iter특수 메서드 호출/실행
> 			리스트 객체 > 이터레이터 객체됨.
> 				그리고 for문 시행이 될 떄마다 next 특수 메서드가 호출되어 1개씩 반환/출력되는 것.


- 이미지
	![](https://blog.kakaocdn.net/dn/Fgpc7/btqRL2k4XBM/4DeoJZ85F4hGCr1cqKM8rk/img.png)
- 위 이미지와 같은 코드 상황
```python
a = [1,2,3,4,5]
print(a)
=>
[1,2,3,4,5]

a = [1,2,3,4,5].__iter__()
print(type(a)) # list_iterator
print(a)
=>
<class 'list_iterator'>
<list_iterator object at 0x0000028F1F670340> # 있는 그대로 객체값이 출력됨. 따라서 반복문을 사용해 = next메서드를 호출해 하나씩 출력해야함.
```


Note: 이러한 작업은 구글 프레젠테이션 도구로 만드는 거구나
**StopIteration 예외가 발생**하면 순회를 마칩니다.

-----
### ㅡ 직접 Iterator 만들기
Note: 제목
ㅡ
Iterator는 직접 만들 수도 있습니다.
	
==**__iter__메소드**를 구현한 클래스를 통해 Iterable한 객체를 만들 수 있==고, ==**__next__메소드**를 구현한 클래스를 통해 Iterator를 만들 수도 있==습니다.

ㅡ
예제에서는 **숫자를 입력받아 1부터 입력받은 값까지 1씩 증가하는 Iterator를 만들어보겠습니다.**
```python

class Iterable:
    def __init__(self, stop_number):
        self.stop_number = stop_number # 종료 값

    def __iter__(self):
        return Iterator(self.stop_number)
```
결과 =>
Iterable한 객체를 만들 수 있는 클래스를 먼저 만들었습니다.
	
`__init__`메소드를 통해 입력받은 값(stop)을 저장하고
		
`__iter__`==메소드에서는 Iterator객체를 리턴하게끔 구현==하였습니다.
	=> 복기
	`__iter__`있다면 Iterator객체가 된다.
	

- 이제 Iterator 클래스를 구현
```python
class Iterator:
    def __init__(self, stop_number):
        self.current_number = 0 # 현재 값
        self.stop_number = stop_number # 종료 값

    def __next__(self):
        if self.current_number < self.stop_number:
            self.current_number += 1
            return self.current
        else:
            raise StopIteration

```
결과=>
ㅡ
Iterator 클래스는 위와 같이 구성

==`__next__`메소드에서 로직을 구현==하였는데, **단순히 ==종료 값보다 현재 값이 작다면 현재 값에 1을 더하고 그 값을 리턴하는 로직**==입니다. **현재 값이 종료 값과 같거나 커지면 StopIteration 예외를 발생**시킵니다.

-----

- 전체적인 코드
```python
class Iterable:
    def __init__(self, stop):
        self.stop = stop

    def __iter__(self):
        return Iterator(self.stop)


class Iterator:
    def __init__(self, stop):
        self.current = 0
        self.stop = stop

    def __next__(self):
        if self.current < self.stop:
            self.current += 1
            return self.current
        else:
            raise StopIteration


test = Iterable(5).__iter__()
print(test.__next__()) # 1
print(test.__next__()) # 2
print(test.__next__()) # 3
print(test.__next__()) # 4
print(test.__next__()) # 5
print(test.__next__()) # StopIteration 예외 발생

```
결과=>
보시다시피 전체적으로 잘 동작하는 것을 확인할 수 있습니다



-----
- 코드
```python
class IterableAndIterator:
    def __init__(self, stop_number):
        self.stop_number = stop_number # 종료 값 지정
        self.current_number = 0 # 현재 값 지정

    def __iter__(self):
        return self # 자기 자신 객체를 리턴

    def __next__(self):
        if self.current_number < self.stop_number:
            self.current_number += 1
            return self.current_number
        else:
            raise StopIteration

```
결과=>

==**Iterable 클래스와 Iterator 클래스를 한번에 구현할 수도 있==습니다.**

차이점이라면 ==**__iter__메소드와 __next__메소드를 같이 구현==했다는 점**
	
그리고 **__iter__메소드가 자기 자신의 객체를 리턴한다는 점** 정도가 되겠습니다.
	
한번 직접 구현해보시면 어떤 원리로 동작하는지 이해가 좀 더 빨리 되니 아직 어떻게 구현하는지 감이 잘 안잡히시는 분들은 간단한 예제를 몇개 만들어보시길 추천드립니다.(1씩 값이 감소하는 Iterator 등)





---
### 출처-참고자료=>
- 

