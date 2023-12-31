---
{"dg-publish":true,"permalink":"/distribute/python/python-table-of-contents/","tags":["파이썬","목차","배포"],"noteIcon":""}
---

### 날짜 2023-10-11 12:05

# 참고/연관된 기록 =>
- https://wikidocs.net/book/1

---
# Second-Brain
![Pasted image 20231129151220.png](/img/user/%EC%B2%A8%EB%B6%80%ED%8C%8C%EC%9D%BC/Pasted%20image%2020231129151220.png)


-------------------------------
# ㅡ [[파이썬 코드 구조_로직_형태 분석\|파이썬 코드 구조_로직_형태 분석]]
##### ㅡ [[distribute/Python 파이썬/Content record folder/중첩클래스-내부클래스-코드구조\|중첩클래스-내부클래스-코드구조]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 특정 클래스 내부에 다른 클래스가 정의되어 있는 형태= 내부 클래스 = 중첩 클래스 구조
	
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 
```python
import my_module

# my_module 모듈 내의 MyStaticClass 클래스의 정적 메서드 호출
result = my_module.MyStaticClass.static_method()
```
- 
```python
import datetime

print(datetime.datetime.now())
```
- 
```python
basedir = os.path.abspath(os.path.dirname(__file__))
```

- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- SQLAlchemy의 `db.session` 코드 구조
		- `SQLAlchemy` 클래스의 인스턴스를 생성할 때 동시에 `self.session` 속성도 `Session` 클래스의 인스턴스로 초기화
			- 일반적인 속성 명명 관행
		- 여러 클래스가 서로 연결되어 있는 경우
			- 구성관계 - 한 클래스가 다른 클래스 객체를 소유_포함하고 있는 상황 
				= 한 클래스가 다른 클래스를 생성하고 한 클래스의 속성이 다른 클래스의 인스턴스가 되는 구조 
				= SQLAlchemy의 클래스에 `session` 객체가 있다 
				= SQLAlchemy클래스가 `session` 객체를 생성하고 있다.
				
			- 연관관계 - 서로 다른 클래스가 서로 상호작용_연결되어 있는 상황
		- 객체 지향 프로그래밍에서 클래스 간 상호작용과 데이터를 공유/구현하는 방법 중 하나
	```python
	db.session.add_all([jose, toy1, toy2])
	db.session.commit()
	```
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 파이썬 코드 구조
		- 모듈들간의 기능 조합으로 인한 기능 확장 = 유연성 향상 
			- 모듈간 기능 확장 예시
			- `os.path`

- VScode에서 코드 설명 부분 의미

> [!NOTE]
> ```
> # 라이브러리에 있는 폰트를 가져온다
> font = pygame.font.Font('freesansbold.ttf', 20)
> 
> (variable) font: Font
> ```
> => "font는/변수(variable)는 Font 클래스의 인스턴스임"
> 즉 클래스의 인스턴스가 생성된 이후 변수는 이렇게 설명이 나오는 군


----
# 02장 파이썬 프로그래밍의 기초, 자료형

##### ㅡ 02-1 숫자형

##### ㅡ 02-7 불 자료형

##### ㅡ "타입" 용어
	
> [!NOTE]
> "데이터 타입"이라는 용어는 파이썬에서 변수가 어떤 종류의 데이터를 저장하고 다루는지를 나타내는 것으로 사용됨.
> 	
> 이 용어는 **데이터의 특징**과 **종류**를 모두 포함하고 있음.
> 즉, "데이터 타입"은 파이썬 언어의 종류 및 특징을 설명하는데 사용되며, 특정 변수나 값이 어떤 종류의 데이터를 나타내는지를 가리킵니다. 

##### ㅡ "문법" 용어
	
> [!NOTE]
> 프로그래밍 언어에서 "문법"이라는 용어는 "코드 작성 방법_규칙" 의미를 가지고 있음

##### ㅡ [[파이썬-연산자\|파이썬-연산자]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 산술 연산자 (Arithmetic Operators)
	- 비교 연산자 = 관계 연산자 (Comparison (i.e., Relational) Operators)
		- `>`
	- 논리 연산자 (Logical Operators)
		- and/ or/ not
	- 삼항 연산자(Ternary operators)
	- 비트 연산자 (Bitwise Operators)
	- 할당 연산자 = 복합 대입 연산자 (Assignment Operators)
		- `=`
	- 구성원 연산자 = 멤버 연산자 (Membership Operators)
		- in/not
			- 멤버 연산자 + 예약어 
	- 식별 연산자 (Identity Operators) = 아이디 연산자
		- is / is not

##### ㅡ [[예약어-키워드\|예약어-키워드]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- del
##### ㅡ [[distribute/Python 파이썬/Content record folder/이터레이터(Iterator) 타입-Iterable 이터러블 특징\|이터레이터(Iterator) 타입-Iterable 이터러블 특징]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 이터레이터 - iterator
		- "다음 값을 리턴할 수 있는 객체"
		- `__iter__()` 메서드
		- `__next__()` 메서드
	- iterable-이터러블
		- "내부 요소(member 멤버)를 하나씩 리턴할 수 있는 특징을 가진 객체" = "여러 요소를 순회할 수 있는 객체"
			- "순회 가능한 객체" = "순서가 있는 객체" = "인덱스가 있는 객체"
			- 특징만 가지고 있을 뿐 스스로 다음 값을 반환할 수 없기 때문에 아직 이터레이터 객체 x
				- ex) 리스트는 이터러블한 객체이지만 이터레이터 객체는 아님


##### ㅡ [[distribute/Python 파이썬/Content record folder/객체특징-얕은복사-깊은복사-메모리주소\|객체특징-얕은복사-깊은복사-메모리주소]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 객체의 특징
		- Mutable - 변경/수정 가능한 자료형
			- 리스트 타입
			- 얕은 복사(Shallow Copy)
				- "원본 객체 주소값만을 복사한 상태"
				- 주소값 같다 = 객체 동일
				-
		- Immutable - 변경/수정 불가능한 자료형
			- int 타입
			- 깊은 복사(Deep Copy) - 원본 배열 보존
				- "원본 객체 자체를 복사한 상태" 
				- 새로운 주소 값 = 새로운 객체
				-
		- copy모듈 - deepcopy()
		- 클래스의 copy() 함수
		- 리스트 슬라이싱

##### ㅡ [[distribute/Python 파이썬/Content record folder/시퀀스-컬렉션-타입\|시퀀스-컬렉션-타입]]
###### ㅡ 02-4 튜플 자료형
###### ㅡ 02-5 딕셔너리 자료형
- 참고기록 : [[Part3-Javascript-내용기록#ㅡ 추가내용\|Part3-Javascript-내용기록#ㅡ 추가내용]]
###### ㅡ  02-6 집합 자료형
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 시퀀스 타입 - sequence
		- 순서 존재 데이터 타입
			- "순서가 있다" = "인덱스가 있다" = "항목들에 접근 가능" = "조작이 가능"
		
	- 컬렉션 타입 - Collection
		- 자료구조 구현 데이터타입
		- "여러 요소(객체들..)를 하나의 단위로 저장/관리할 수 있는 특징을 가진 데이터 타입"
		- 리스트-튜플-set-딕셔너리
		
	- 타입의미 복기
		- 데이터 종류, 특징
		- ex) 리스트는시퀀스 타입(특징)+ 컬렉션 타입(데이터 종류)


### ㅡ [[distribute/Python 파이썬/Content record folder/02장 파이썬 프로그래밍 기초-자료형/02-2 문자열 자료형\|02-2 문자열 자료형]]

##### ㅡ 문자열 포매팅
- ㅡㅡㅡㅡㅡㅡㅡ
- 1. %기호 사용한 포맷코드
	- 숫자 대입
	- 문자 대입
	- 변수 대입
	- 
	- %기호+숫자
		- 1. 정렬 표현 가능
			- 왼쪽/오른쪽/가운데 정렬
		- 2. 공백 표현 가능
		- 3. 소수점 표현 가능
- 2. format 메서드 
- 3. f-string 
###### ㅡ [[distribute/Python 파이썬/Content record folder/문자열 관련 함수\|문자열 관련 함수]]
- 키워드/문장 요약 =>
	join()

### ㅡ [[distribute/Python 파이썬/Content record folder/02장 파이썬 프로그래밍 기초-자료형/02-3 리스트 자료형\|02-3 리스트 자료형]]

- 리스트
- ㅡㅡㅡ
- 요소-element
- 특징
	- 리스트 안 요소 다양한 타입 가능
	- 다중 리스트
	- 값 변경 가능 mutable type
	- 인덱스/인덱싱
	- 슬라이싱 (slicing)
		- 역순 출력 가능-[: : -1] 
- 리스트 연산
	- 리스트 더하기
	- 리스트 반복하기
		- 곱셈 연산자
- 리스트 길이
	- 리스트 확장 - "하나의 리스트에 다른 리스트 연결"
### ㅡ 리스트 자료형 관련 함수
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- insert(index, 넣을 값)
	- 리스트 요소 삽입
- pop(index)
	- 원본 객체/리스트 요소 추출
	- 딕셔너리 자료형 사용 가능
- remove("값")
- append() - "요소 추가"
- sort() - "리스트 정렬"
	- 오름차순 <> 내림차순
	- sorted() 내장함수 - "리스트 메서드-원본 리스트 정렬 변경 <> 내장함수 새로운 리스트 반환출력"
- reverse() - "리스트 모든 요소 역순/뒤집기"
- index() - "인덱스 반환"
- count() - "리스트에 포함된 요소 개수 확인"

### ㅡ 02-8 자료형의 값을 저장하는 공간, 변수
### ㅡ [[distribute/Python 파이썬/Content record folder/파이썬-변수의미-명명규칙-예약어\|파이썬-변수의미-명명규칙-예약어]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 파이썬 변수란
		- "값이 직접 들어가 있는 상태가 아닌 대입된 객체를 가리키는 포인터같은 상태" = "변수에 메모리 주소값이 할당"
		
	- 변수가 필요한 이유
		- "프로그램이 돌아가기 위해선 데이터 필요 > 그러한 데이터는 메모리 공간에 존재 > 메모리 공간에 접근/참조하기 위해선 이름/주소값 필요"
		
	- 파이썬 객체지향
	- 변수 명명규칙
		- 영문자/숫자/언더스코어 가능
		- 숫자로 시작 x
		- 대소문자 구분 ㅇ
		- 미리 정의된 예약어(reserved words) x





### ㅡ [[distribute/Python 파이썬/Content record folder/네임스페이스-내장변수-__name__-객체참조탐색순서-LEGB\|네임스페이스-내장변수-__name__-객체참조탐색순서-LEGB]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 내장변수=전역변수 - "이미 정의되어 있는 변수 = 파이썬 언어가 가지고 있어야 하는 기본 설정값들이 저장되어 있는 느낌"
		- `__name__`
			- `__main__`
		- 존재 이유/배경 
			- "이름뿐 아니라 다른 방법으로도 객체를 구분할 수 있는 추가적인 방법 필요"
			- "파이썬 개발자들이 저지를 수 있는 실수를 막아준다"
	- 네임스페이스(Namespace) | [[네임스페이스-접근제어-객체\|네임스페이스-접근제어-객체]]
		- 코드블럭
		
	- 객체 참조 탐색 순서
	- LEGB 
		- 지역 네임스페이스(Local namespace)
			- 함수/메서드단위 코드블럭-범위
		- 글로벌 네임스페이스(Global namespace)
			- 모듈단위 코드블럭-범위
		- 빌트인 네임스페이스(Built-in namespace)
			- 전체코드 
		- 상위 네임스페이스
		
	- 코드파일을 "직접 실행" 표현
		- "인터페이스를 통해 실행"
	- 코드파일을 "모듈로서 사용_실행" 표현
		- import

### ㅡ [[네임스페이스-접근제어-객체\|네임스페이스-접근제어-객체]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 네임스페이스(Namespace)
		- 이름 = 식별자
		- "객체(변수-함수-모듈-클래스)의 이름/식별자를 저장하고 관리하는 공간 = 객체를 구분할 수 있게됨 = 객체마다 행사할 수 있는 범위 제한하여 이름 중복 허용됨 = 객체 유효 범위"
		- 
	- 접근 제어(Access Control) (기능 의미) <> 접근 제어자 (`public`, `private`, `protected` 코드 의미)
		- "접근하다" = "사용하다" = "참조하다"
		- "클래스 내 멤버" = 변수, 메서드
		- "클래스 내 멤버에 대한 외부에서의 접근 권한을 관리"


### ㅡ [[distribute/Python-Chrome Dinosaur Game-Project/Content record folder/전역상수(변수)-모듈화된구조\|전역상수(변수)-모듈화된구조]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 전역 상수(변수) <> 변수
	- 명명 규칙/관례
		- 대문자 작성
	- 특징
		- 프로그램 실행 중 수정 x
	- "모듈화된 구조로 프로그램을 작성했다" 표현, **"모듈 수준에서 정의되어 사용된다"** 의미


### ㅡ [[네임맹글링(name mangling)-`_클래스명__속성명`]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 네임 맹글링(name mangling)
	- 언제 사용?
		- 클래스 속성값을 외부에서 접근하기 힘들게 할 때
			- "클래스의 속성값을 외부에서 접근하고 있다" 
			- [[네임스페이스-접근제어-객체\|private한 성격]]
			- "맹글링이 적용된 속성"
				- `_클래스명__속성명`
		- 하위 클래스에서 상위 클래스 속성을 오버라이딩 하는 것을 막을 때


### ㅡ [[`_` 언더바-언더스코어 기능 및 명명규칙]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- `_` 언더바 - 언더스코어 역할
	- 무시하는 값
		- `*`(Asterisk_아스테리스크)
		- 언패킹 (Unpacking)
	- 숫자와 함께 사용 > 자릿수 구분
	- `_`를 사용한 네이밍 (명명규칙) <> 문법적인 요소_규칙
		- 언더바를 이름 앞에 하나 붙은 경우 의미
		- 이름 뒤에 언더바가 하나 붙은 경우 의미
		- 이름 앞에 언더바가 두 개 붙은 경우 의미
			- 네임 맹글링 (name mangling)
		- 이름 앞 뒤로 언더바가 두 개 붙은 경우 의미
			- 매직 메소드(Magic Method) - 던더 메소드(Dunder Method, Double Underscore Method)


------
# 03장 프로그램의 구조를 쌓는다! 제어문
- 
조건문/반복문 모두 제어문이라고 표현함
왜?
특정 조건에 따른/상황에 따라 코드 흐름을 제어하고 싶을 때 조건문/반복문을 사용할 수 있기 때문.

### ㅡ [[조건문-if-elif-else\|조건문-if-elif-else]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- if문
		- pass 키워드
	- 기본 구조
		- if-else
		- elif (else if)
		- 콜론(:)

### ㅡ [[for문-range()\|for문-range()]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- for문 기본구조
	- ㅡㅡㅡㅡ
	- `for 변수 in 문자열(or 튜플 or 리스트):`
	- `for _ in range(N)`
		- 시퀀스 자료형 
			- 리스트-튜플-문자열 
		- 딕셔너리 - "key값에 순서대로 접근/반환"
			- values() 메서드
		- 집합(set)
		- range()함수
	- 
	- range()함수 - "전달된 인수에 따라 연속된 정수들을 반환함수"
		- range 객체 반환
			- list() 리스트 변환
		- 문법
			- `range(마지막정수)` / `range(시작정수, 마지막정수)`/ `range(start, stop, step)`
			- "~이상 ~ 미만"
			- step - "숫자 간 간격 (기본값 1)"
				- 역순출력
				- 
	- for 문과 continue 문


----
# 04장 파이썬의 입출력

# ㅡ [[distribute/Python 파이썬/Content record folder/04-1 함수란\|04-1 함수란]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 함수란 (function)
- 가장 단순한 형태 함수 정의
	- 매개변수(parameter)
	- 인수(arguments)
	
> [!NOTE]
> ㅡ 함수(function)란 무엇인가?
> 하나의 특정 작업/기능을 수행하기 위해 독립적으로 설계된 프로그램 코드의 집합/코드블록
> 	
> ㅡ 함수를 사용하는 이유는 무엇일까?
> 프로그램 내 중복적인 코드 작성 최소화, 코드의 재사용성
> 	 
>  ㅡ 함수 선언하고 호출하기
>  -인수를 전달받지 않는 함수
>  -인수를 전달받아 해당 인수에 따라 다른 동작을 수행하도록 하는 것이 일반적
>  -함수의 선언시 명시된 매개변수의 개수와 같은 수의 인수만을 전달 - TypeError
> 	 
>  ㅡ 매개변수(parameter)
>  함수 호출 시 전달되는 인수의 값을 함수 내부에서 사용할 수 있도록 저장할 함수 내 변수
> 	 
>  ㅡ 인수(arguments)
>  인수 = 인자 = 함수 호출시 입력하는 값 = 입력값 
> 	 
>  ㅡ 일반적인 함수
> 	 함수 내부에서 return 만나면 바로 종료됨
>  ㅡ 입력값이 없는 함수
>  ㅡ 리턴값이 없는 함수
>  ㅡ 입력값도, 리턴값도 없는 함수
> 	 
>  ㅡ 매개변수를 지정하여 호출하기
>  인수 전달 시 매개변수 지정 가능
>  함수에 전달되는 인수는 매개변수에 순서대로 저장 < 함수 호출할 때 대입 연산자 사용 시 인수가 저장될 매개변수 직접 지정 가능
> 	 
>  ㅡ 매개변수의 기본값 설정(default parameters)/ 초기값 설정
>  -함수 호출 시 설정해 놓은 기본값으로 자동 초기화 가능
> 	-주의 - 매개변수 기본값 설정은 오른쪽부터 명시
> 	 
>  ㅡ 입력값이 몇 개가 될지 모를 때는 어떻게 해야 할까?
>  ㅡ 여러 개의 입력값을 받는 함수 만들기
>  ㅡ 가변 매개변수(variable parameters)


### ㅡ [[함수-리턴값에 따른 함수의 형태-용어\|함수-리턴값에 따른 함수의 형태-용어]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 1. 원본값/객체를 수정 후 반환/출력 값이 없는 메서드/함수 존재
		- None 반환 출력
		
	- 1-2. ~ 수정 후 값을 반환/출력하는 메서드/함수 존재
		- pop()
		
	- 2. 원본값/객체를 수정 후 그 수정된 원본 객체를 반환/출력하는 메서드/함수 존재
		
	- 3. 새로운 값을 반환하는 함수 존재 - "단순하게 인수로 들어온 값 > 계산된 결과 값을 반환하는 함수"
		- return
			- "함수를 호출한 곳에 결과값 반환 > 변수 대입 사용"
		- 1. 변수 대입(할당) 후 사용
		- 2. 그대로 바로 사용
		- 일반적인 함수 형태
		- 여러 개 결과값 반환 함수 형태
			- 언패킹
		
	- 4. 새로운 객체를 생성 후 반환하는 메서드/함수 존재
		- "원본 객체 변경하지 않고 새로운 객체 생성"
		- 리스트 슬라이싱


##### ㅡ [[distribute/Python 파이썬/Content record folder/리스트 슬라이싱-슬라이스 객체\|리스트 슬라이싱-슬라이스 객체]]
###### ㅡ [[distribute/Python 파이썬/Content record folder/리스트-슬라이싱-복사-del-슬라이스 객체-사진\|리스트-슬라이싱-복사-del-슬라이스 객체-사진]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 리스트 슬라이싱-슬라이스 객체
	ㅡ
	del 예약어-문제풀이 사진확인
		
	리스트 슬라이싱 > 메모리 상에 새로운 객체 반환출력됨
		= 객체가 복사된 상태
	하지만, 슬라이싱을 하더라도 변수에 할당하는 과정이 없다면 "슬라이스 객체"임
		: 새로운 리스트 객체가 반환된 상태가 아닌, 원본 객체 일부분을 참조하고 있는 객체일 뿐


### ㅡ [[distribute/Python 파이썬/Content record folder/유효범위-지역-전역변수\|유효범위-지역-전역변수]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 변수-유효범위 (variable scope)
	- 지역 변수(local variable)
		특정 함수에서만 사용되는 값들
	- 전역 변수(global variable)
		여러 함수에서 함께 사용하는 값들





### ㅡ [[distribute/Python-Chrome Dinosaur Game-Project/Content record folder/함수설명(독스트링)-타입힌트(Type Hint)\|함수설명(독스트링)-타입힌트(Type Hint)]]
##### ㅡ [[distribute/Python 파이썬/Content record folder/타입힌트-추가 설명\|타입힌트-추가 설명]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 함수 설명(docstring) 작성방법
- 타입 힌트(Type Hint) 표현식 
	함수 이름 / 매개변수 개수 / 매개변수 자료형_타입 / 매개변수 기본값 / 함수 반환값 자료형 (자료형 = 데이터 타입 = 클래스)
- 함수의 독스트링(docstring)
	- "함수가 어떻게 정의되어 있는지 설명하다." <> "함수 동작 방식과 사용법을 설명하다" 

### ㅡ [[distribute/Python 파이썬/Content record folder/타입힌트용 클래스-타입힌트기호\|타입힌트용 클래스-타입힌트기호]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 타입 힌트
	- 파이썬 객체지향
		- Optional 클래스
		- Literal 타입 힌트용 클래스
	- | 기호
	- = 기호
	- [] 괄호


--------


### ㅡ [[distribute/Python 파이썬/Content record folder/매개변수 2가지 역할-옵션매개변수\|매개변수 2가지 역할-옵션매개변수]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
ㅡ 메서드/함수 **매개변수** 두 가지 주요 **역할** 수행.
1. 외부 인수 받는 단순 변수로서 역할 수행
	
2. 기존 함수의 기능에 추가적인 설정, 동작 제어 역할 수행 (**옵션** - 설정 - 매개변수)
이러한 설정은 특정한 매개변수에 특정한 인수를 할당함으로서 함수 내부에서 기존 동작을 변경 or 조절.

### ㅡ [[distribute/Python 파이썬/Content record folder/매개변수-지정호출-기본값 설정\|매개변수-지정호출-기본값 설정]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 함수 매개변수-parameter
	- 매개변수 지정 호출
	- 매개변수 기본값 설정 - default parameters

### ㅡ [[distribute/Python 파이썬/Content record folder/가변매개변수-위치매개변수-키워드매개변수\|가변매개변수-위치매개변수-키워드매개변수]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- `(*args, **kwargs)`
	- 가변 인수_가변 매개변수 (variable-length arguments)
	- 함수 인수 전달 2가지 방법
		- 위치 매개변수_인수 (Positional Arguments)
			- `*args`
				- 튜플
		- 키워드 매개변수_인수 (Keyword Arguments)
			- `**kwargs`
				- 딕셔너리
	

### ㅡ [[distribute/Python 파이썬/Content record folder/메서드-함수\|메서드-함수]]
: 함수와 메서드는 개념적으로 유사하지만, 메서드는 특정 객체에 속해 있는 함수를 의미.


### ㅡ [[distribute/Python 파이썬/Content record folder/람다표현식-익명함수\|람다표현식-익명함수]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 람다 표현식(Lambda expression) =익명 함수(Anonymous function) = 이름이 없는 함수 - "간단하게 함수 정의 > 사용하는 표현방법"
	- ㅡㅡㅡㅡ
	- 사용법-작성법-표현식
	- 람다 표현식 언제 사용
		- 1. "람다 표현식은 함수-매개변수로서 많이 활용" 표현 = 람다 표현식으로 만들어진 함수 그 자체를 다른 함수의 매개변수로서 사용
		- 2. 재사용하지 않는 간단한(한 줄로 표현 가능) 함수일 때



-----
# 05장 파이썬 날개 달기
	
05장에서는 클래스와 함께 모듈, 예외 처리 및 파이썬 라이브러리에 대해서 알아보자. 05장을 끝으로 여러분은 파이썬 프로그램을 작성하기 위해 알아야 할 대부분의 내용을 배우게 된다.

### ㅡ 05-1 클래스
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>

> [!NOTE]
> ㅡ 함수 < 클래스 < 모듈
> ㅡ 파이썬-함수
> 는 특정한 기능을 구현하는 작은 코드 블록
> 	
> ㅡ 파이썬-클래스
> 는 그러한 함수들을 그룹화해서 가지고 있는 큰 코드블록
> 	
> 클래스는 데이터(/변수-속성), 기능(/함수/메서드)를 묶어서 저장하고 있는 큰 코드블록
> 	
> 클래스마다 특정 데이터 타입/처리에 관련된 메서드와 속성을 포함 가능
	
> [!NOTE]
> ㅡ
> 자바 클래스 개념 <> 파이썬 모듈 개념 비슷
> 	
> 자바 클래스는 코드 블록과 코드 파일 의미를 동시에 가지고 있다면 <> 파이썬에선 구분
> 	
> 파이썬 모듈 - 코드 파일 (확장자 .py)
> 하나의 파이썬 코드 파일 안에 여러 개 클래스, 함수 등 포함가능
> 	
> 파이썬 클래스 - 코드 블록

- 클래스 명명 규칙
	ㅡ 문자로 시작 (숫자로 시작 x)
	ㅡ 문자, 숫자, 밑줄(`_`)로 구성될 수 있음
	ㅡ 공백을 포함 X  
	ㅡ 파이썬 예약어와 동일X
	ㅡ 일반적으로 대문자로 시작
		파이썬의 관례(convention) - 클래스 이름을 소문자로 시작해도 파이썬에서는 문법적으로 문제 X

- 파이썬에서 클래스란?
	클래스 내부에는 다양한 속성_변수들 존재, 다양한 동작을 구현하는 메서드 존재
	
- 파이썬 크롬 게임 프로젝트 복기 =>
	모든 것이 객체단위였음
		
	ex) 
	게임 화면도 클래스 정의 > 인스턴스 생성_객체를 생성.
	공룡 캐릭터 존재 > 공룡 클래스 정의 > 내부에 다양한 설정값_속성값 정의 + 동작_메서드 정의 하면서 구현
	
- 플라스크 웹 프레임워크 복기 =>
	ex)
	데이터베이스라는 프로그램 존재.
	이 프로그램에는 입력된 데이터를 저장하기 위한 다양한 설정값들과 기능들이 존재.
		
	플라스크 웹 프레임워크 코드를 이용해 파이썬 코드 파일 내부에서 데이터베이스 기능을 구현/사용하기 위해서 데이터베이스의 다양한 기능과 설정들을 적절한 클래스를 사용했음
		
	파이썬 플라스크 웹 프레임워크 코드를 분석하다보면 하나의 객체안에 다른 객체들이 연결?되어 있음.
	그 이유는 여러 기능들, 설정값들이 모여 하나의 데이터베이스 프로그램을 구현하기 때문. 
		
	이처럼 여러 기능들이 모여서 데이터베이스 프로그램이 동작하는 것 처럼 여러 클래스들이 결합되어 DB클래스가 만들어져있음

##### ㅡ [[distribute/Python 파이썬/Content record folder/클래스객체-클래스인스턴스-용어\|클래스객체-클래스인스턴스-용어]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 클래스 객체(Object) <> 클래스 인스턴스(Instance) 용어
	- 클래스 객체 생성
		- 메모리 생성
		- `__new__` 메서드
	- 클래스 인스턴스 생성
		- 객체에 값 할당
		- `__init__` 메서드

##### ㅡ [[distribute/Python 파이썬/Content record folder/파이썬(python) - 클래스(class)의 특징\|파이썬(python) - 클래스(class)의 특징]]
###### ㅡ [[distribute/Python 파이썬/Content record folder/클래스-생성자-사용이유-예시코드\|클래스-생성자-사용이유-예시코드]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 클래스 정의 이유 - 예시코드
	- 클래스 - 생성자 메서드 정의 이유 - 예시코드
	
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 클래스 특징
		- 1. object 클래스 - 최상위 클래스
		- 2. 데이터 - 클래스 인스턴스 - 객체 - "모든 자료형은 클래스다."
	- 메서드
		- 인스턴스 메서드(Instance method)
			- self 코드
		- 클래스 메서드(Class method)
			- cls 코드
			- "직접 인스턴스를 생성 = 직접 값을 초기화"
		- 스태틱 메서드(Static method) = 정적메서드
	- 클래스 변수
	- 인스턴스 변수
		ㅡ
		파이썬 클래스 내부에 존재하는 변수_데이터를 "속성 (attributes), 필드 (fields)" 부름


###### ㅡ [[distribute/Python 파이썬/Content record folder/클래스 계층구조-최상위-메타-사용자정의클래스\|클래스 계층구조-최상위-메타-사용자정의클래스]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 클래스 계층구조
		- 최상위 클래스 = object 클래스 - 모든 메타클래스의 부모 클래스
			- 메타클래스 - 모든 클래스의 부모 클래스
				- 사용자 정의 클래스 = 일반 클래스

##### ㅡ [[distribute/Python 파이썬/Content record folder/클래스상속 (inheritance)-메서드오버라이딩 (method overriding)\|클래스상속 (inheritance)-메서드오버라이딩 (method overriding)]]
- 상속예시 : [[distribute/Python-Chrome Dinosaur Game-Project/Content record folder/파이썬 크롬 프로그램 코드를 작성하면서 느낀 점#상속\|파이썬 크롬 프로그램 코드를 작성하면서 느낀 점#상속]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 클래스 상속 (inheritance)
		- 부모 클래스(parent class) = 기초 클래스(base class)
		- 자식 클래스(child class) = 파생 클래스(derived class)
	- 메서드 오버라이딩(method overriding)

##### ㅡ [[distribute/Python 파이썬/Content record folder/MRO-다중상속-다이아몬드\|MRO-다중상속-다이아몬드]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>


##### ㅡ [[distribute/Python 파이썬/Content record folder/특수속성-MRO\|특수속성-MRO]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 메서드 결정 순서(Method Resolution Order)
		- 특수 속성(dunder/magic attribute)
		- 언더스코어(`__`)
			- [[`_` 언더바-언더스코어 기능 및 명명규칙#4.네이밍|매직 메서드]]
		- `__mro__`
		- `dir()` 함수

##### ㅡ [[distribute/Python 파이썬/Content record folder/클래스-super()\|클래스-super()]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 클래스-super()
	- "유지보수" = "중복코드 감소" = "동작 확장" 표현
##### ㅡ [[distribute/Python 파이썬/Content record folder/클래스 내부변수-속성-언더스코어\|클래스 내부변수-속성-언더스코어]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>

##### ㅡ [[distribute/Python 파이썬/Content record folder/정적메서드\|정적메서드]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 정적메서드
	- 정의 방법 2가지
	- @staticmethod - 데코레이터 표현식
	- 일반 메서드
	
클래스 인스턴스 생성 x > 클래스로 직접 참조 사용 가능

##### ㅡ [[생성자(메서드)(`__init__`)-인스턴스생성]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 생성자(메서드) = 생성자(`__init__`) = constructor
		이름 그대로 생성자 메서드 덕분에 클래스를 정의하고 클래스를 호출하면 클래스의 인스턴스가 생성되는 것
	- "생성자 메서드를 (자동)호출하다" <> "생성자 메서드를 직접 호출하다."
	- 기본 생성자(메서드)
	- 클래스의 인스턴스 생성 과정


##### ㅡ [[distribute/Python 파이썬/Content record folder/매직메서드-특수-__str__-__repr__\|매직메서드-특수-__str__-__repr__]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- 매직 메서드(Magic Method) - 특수 메서드
	- `__str__`
	서로 다른 데이터 타입들간 인터페이스 기능
	- `__repr__`
	단순 표현
	
- 공통점
	- 객체 문자열 반환
- 클래스 인스턴스 <> 내장함수


##### ㅡ [[distribute/Python 파이썬/Content record folder/tk.TK()-tk.Tk-코드구조-클래스 직접참조\|tk.TK()-tk.Tk-코드구조-클래스 직접참조]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- `tk.TK()` - 클래스 생성자 메서드를 참조_사용 표현
- `tk.Tk` - 클래스 자체를 참조_사용 표현 
	- "클래스를 직접 참조_사용" 경우
		- 1. 모듈에서 클래스를 가져와 사용 시
		- 2. 클래스의 정적 속성-메서드 사용 시
		- 3. 클래스를 상속 시

### ㅡ 05-2 모듈
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
ㅡ 파이썬 모듈 - 코드 파일 (확장자 .py)
	하나의 파이썬 코드 파일 안에 여러 개 클래스, 함수 등 포함가능


##### ㅡ [[distribute/Python 파이썬/Content record folder/모듈 불러오기-import구문\|모듈 불러오기-import구문]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- import 구문
	- import 모듈명
	- from 모듈명 import`*`
	- from 모듈명 import 함수명 또는 클래스명

### ㅡ 05-3 패키지 (Package)
ㅡㅡㅡㅡㅡㅡㅡㅡ
- 키워드/문장 요약=>
	ㅡ 폴더 = 디렉토리 = 패키지
	ㅡ 서브패키지 (Subpackage) = 하위 패키지
	
	ㅡ
	패키지 용어 <> 라이브러리 용어 혼용해서 설명됨.
	ex) 라이브러리를 가져와 사용하더라도 에디터 프로그램에서는 모듈로 인식됨

### ㅡ  [[distribute/Python 파이썬/Content record folder/05장 파이썬 날개 달기/05-5 내장 함수\|05-5 내장 함수]]
	파이썬에서 미리 만들어 제공해 주는 함수
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
- list()
- help()
- isinstance()
- enumerate()
- type()
- zip()
- str()
- max()
- map()
- dir() : 
	[[distribute/Python 파이썬/Content record folder/클로저-함수-속성-변수유효범위#Q. 그렇다면 클로저는 대체 어디에 존재하는 걸까요?\|참고자료]]







### ㅡ 05-6 표준 라이브러리
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>


ㅡ 
- 파이썬 코드 구조
	- 함수 < 클래스-(메서드) < 모듈 < 라이브러리 <> 패키지 <> 프레임워크 
- 클래스
- 파이썬 모듈	
- 라이브러리
- 프레임워크
	
	ㅡ
	내장함수와 메서드는 호출하는 방법 달라 => 
		`함수이름(인자)` <> `객체.메서드이름(인자)`
		
	ㅡ
	클래스는 객체를 생성하기 위한 템플릿/포맷/틀/(붕어빵 금형)
		
	클래스 내부에서 객체의 상태_속성_데이터와 동작_기능 정의함.
	따라서 클래스는 내부는 -  속성_변수 와 메서드_함수로 구성.
	
	ㅡ
	모듈은 파이썬 코드 (단일) 파일.
		= 함수 변수 클래스 등등 코드의 집합.
		
	다른 파이썬 프로그램에서 import하면서 재사용 가능
		
	구조
		라이브러리
			모듈
	파이썬 모듈은 라이브러리의 한 부분임.
	따라서 모듈을 라이브러리라고도 혼용해서 부름.
		
	패키지_디렉토리 구조
		디렉토리1
			모듈1
		디렉토리2
			모듈2
	따라서
	패키지는 모듈들의 집합.
	디렉토리 구조로 비슷한 주제, 기능을 가진 코드들 구조화 가능.
		
	라이브러리는 기능들의 집합체 <> 패키지는 라이브러리, 모듈등을 구조화해서 묶어놓은 단위 느낌
		따라서 패키지가 좀 더 큰 단위/묶는 단위
	
	ㅡ 
	라이브러리 : 재사용 가능한 코드들의 집합
		= 함수 클래스 모듈 등이 한번에 묶여 있는 집합체
		
	디렉토리_폴더처럼 구조적으로 묶여있는 상태가 아니라 하나의 큰 폴더_큰 파일안에 다 들어있는 느낌이라 생각.
		
	작은 단위 코드 조각들로 구성되어 있어 필요한 기능을 불러와 사용.
		= 따라서 라이브러리 단위는 함수 하나, 클래스 하나, 모듈 하나 단위임
	
	ㅡ 
	웹 프레임워크 - 웹 애플리케이션 개발하기 위해 사용되는 도구들의 모음
		
	도구들은 파이썬 코드로 작성된 모듈 형태로 제공.
	각각 모듈이 웹 개발에 필요한 기능들을 제공.
		
	구조
		웹 프레임워크
			모듈 
	따라서 웹 프레임워크를 모듈이라고 혼용해서 부름.

### ㅡ 05-7 외부 라이브러리
: 파이썬은 데이터 분석에 이상적인 언어로, 넘파이(NumPy), 판다스(Pandas), 맷플롯립(Matplotlib) 등과 같은 라이브러리들을 활용하여 데이터 처리, 통계 분석, 시각화를 손쉽게 수행할 수 있다.
	
참고기록 : [[distribute/Python-Chrome Dinosaur Game-Project/Content record folder/콜라이더-충돌박스-사각형-피격범위#ㅡ 외부 라이브러리_프레임워크 이해\|콜라이더-충돌박스-사각형-피격범위#ㅡ 외부 라이브러리_프레임워크 이해]]
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

##### ㅡ [[distribute/Python 파이썬/Content record folder/파이썬-cmd-명령코드\|파이썬-cmd-명령코드]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	다른 기록들에서 나온 명령코드들을 
	하나의 기록에 연결
	마치 특정 과목에 대한 "목차-기록"처럼
- pip - 프로그램-코드
	- list
	- show
- python 코드


----
# 07장 파이썬 날아오르기
: 이 책을 다 읽은 후 자신에게 필요한 파이썬 프로그램을 만들어 볼 것. 
	
간단한 프로그램이 아니라면 이때 반드시 파이썬 표준 라이브러리를 사용해야 하는 순간이 온다. 하지만 파이썬 표준 라이브러리 가운데 몇 가지는 앞에서 배우지 않은 고급 개념을 미리 알아야만 이해할 수 있다. 
07장에서는 이 개념에 대해 알아본다. 


### ㅡ [[distribute/Python 파이썬/Content record folder/데코레이터함수-표현식\|데코레이터함수-표현식]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 데코레이터 Decorator (함수)
		- "꾸며주는 기능을 수행하는 함수" = "기존의 함수 앞, 뒤로 로직을 추가한다"
		- [[distribute/Python 파이썬/Content record folder/일급객체(first-class citizen)-조건\|일급 객체(First class citizen)]]
		- [[distribute/Python 파이썬/Content record folder/클로저-함수-속성-변수유효범위\|클로저(Closure)]]
		-
	- 데코레이터 함수 사용 장-단점
		- "코드 중복 최소화" = "재사용성 증가" = "수정하기 용이함"
		-
	- 데코레이터 특징
		- 데코레이터 함수 - func 매개변수
		- "다른 함수가 인자로 전달" = "인자로 데코레이터를 적용할 함수를 전달"
		-
	- 데코레이터 표현식 `@`
		- "서로 다른 함수가 연결되어 있다"
		- "함수 자체를 반환한다" <> "함수를 실행한 결과를 반환한다"
		-
	- 데코레이터 동작순서/흐름
	- `__call__`

##### ㅡ [[distribute/Python 파이썬/Content record folder/클로저-함수-속성-변수유효범위\|클로저-함수-속성-변수유효범위]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 클로저 (Closure)
		- 1. 클로저 함수 
		- 2. 클로저 속성(클래스 변수) - `'__closure__'`
			- "외부 scope에 존재하는 변수 값 저장"
			- 클로저 객체 확인 방법
				- 튜플 타입
				-
		- "특정한 조건을 만족하는/특정한 기능을 수행하는 함수"
		- "데코레이터 함수 내부 함수"
		- 프리변수
		-
	- 변수 유효범위 - 스코프 scope
		- 클로저 속성 필요한 이유
	- "Q. 그렇다면 내부함수가 어떻게 외부 함수 변수를 참조? 사라지는거 아님?"

###### ㅡ [[distribute/Python 파이썬/Content record folder/일급객체(first-class citizen)-조건\|일급객체(first-class citizen)-조건]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 파이썬(python) - 일급 객체(first-class citizen)
		- OPP 사용되는 개념
	- 3가지 조건
		- 변수, 자료구조 타입에 할당 가능
			- "딕셔너리에 함수를 할당했다"
		- 함수-매개변수에 전달 가능
		- 함수-리턴값으로 사용 가능
			- "따라서 파이썬에서 함수는 일급 객체"
	- "함수 객체 호출" <> "함수 호출(내부 코드로직)

##### ㅡ [[distribute/Python 파이썬/Content record folder/매직메서드-종류\|매직메서드-종류]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 매직 메소드(Magic method)
		- "이미 특정한 기능이 정의된 함수"
		- "직접 호출x > 정해진 규칙 호출"
		- "파이썬 모든 데이터는 특정 클래스의 인스턴스/객체" 표현
		- `__add__`
		- [[distribute/Python 파이썬/Content record folder/클래스객체-클래스인스턴스-용어\|__new__]]
		- `__init__`
		- `__del__`
		- `__str__`, `__repr__`
		- `__iter__`
			- [[Python 파이썬-목차-수정#ㅡ 이터레이터(Iterator) 타입-Iterable 이터러블 특징\|iterable하다]]
		- `__next__`
		- `__len__`
		- `__bool__`
		- `__add__`, `__sub__`, `__mul__`, `__truediv__`
		
	- 매직 메서드 구현 연습코드
		- "직접 속성에 접근" 표현
		- "파이썬 객체지향 프로그래밍 언어"

##### ㅡ [[distribute/Python 파이썬/Content record folder/컴프리헨션-표현식\|컴프리헨션-표현식]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 컴프리헨션 표현식 존재 - Comprehension = 리스트 내포
		- 리스트 "
		- 딕셔너리 "
		- 셋 "
		
	- 파이썬 자료구조 (구현한) 타입
	- "간결하게 담는다"




##### ㅡ [[distribute/Python 파이썬/Content record folder/제너레이터-지연평가구현체-컴프리헨션-yield\|제너레이터-지연평가구현체-컴프리헨션-yield]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 제너레이터-Generator 타입/객체 = 지연 평가(Lazy Evaluation) 구현체
		- 이터레이터 타입 생성 객체
		- "lazy 하지 않은 객체" = list 객체
	- 어떻게 생성/사용
		- 1. (제너레이터 생성) 컴프리헨션-comprehension 문법/표기법 사용
		- 2. 함수 내부에 yield 키워드 사용

###### ㅡ [[distribute/Python 파이썬/Content record folder/제너레이터-이터레이터(Iterator)-코드 및 추가설명\|제너레이터-이터레이터(Iterator)-코드 및 추가설명]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	ㅡ
	**이터레이터** 데이터 순회를 가능하게 해주는 객체를 가리키는 용어.
	**제너레이터**는 이터레이터 객체를 생성하는 방법임.
		ㅡ 또 다른 방법. 
		for문을 사용하는 것. 
	
	- 차이점
	ㅡ 이터레이터
	1.컬렉션(예: 리스트, 튜플, 세트) 등의 객체안에 있는 요소들을 순회할 때 사용.
	2.모든 값 한 번에 메모리에 저장.
	3.`__iter__()`와 `__next__()` 메서드를 구현한 클래스로 정의.
		
	ㅡ 제너레이터
	1.함수로 정의됨. = 내부에  yield 키워드 사용.


---
# 출처-참고자료=>
- 


