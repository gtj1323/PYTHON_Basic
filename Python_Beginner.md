[TOC]

# 0. Python 준비.

파이썬의 특징

- 스크립트 언어 : 컴파일 없음. 코드를 컴파일 없이 실행. 컴파일 언어보다 느림. 
- 동적 타이핑 언어 : 선언과 변수를 정의하는 과정에서 타입을 신경쓸 필요가 없다는 장점.
- 절차적 프로그래밍 : 코드를 순서에 따라 실행함.

## 0.1. python 설치.

파이썬을 설치할 때 다양하게 설치가 가능합니다. 

- Python3
  인터넷에 검색하면 쉽게 볼 수 있는 버전입니다. 무료구요. 3.x 버전과 2.x 버전이 있고, 호환이 안되는 부분이 있습니다. 저는 python 3만 다룰껍니다.
- Anaconda
  유명한게 Anaconda가 있습니다. 일반적인 Python에 사람들이 많이 쓰는 모듈(오픈소스 혹은 외부에 이미 만들어져 있는 코드), 다양한 에디터(Jupyter Notebook 등)이 함께 들어옵니다. 용량이 파이썬보다 큽니다.



## 0.2. python 코드 에디터

파이썬코드를 수정할 때 쓰는 에디터는 여러가지 있지만 필자가 써본 에디터 3개만 쓰려한다.

- PyCharm 무료버전 (유료버전 안써봄.)
  각각의 프로젝트가 하나의 가상환경 (새로운 프로젝트에는 새로운 모듈을 설치.)
  가상환경을 따로 설정해줄 필요가 없다는 점에서 장점이 있습니다.
  (매번 새로 만들어주려면 생각보다 귀찮죠.)
- Jupyter Notebook
  각각을 구분해서 실행시킬 수 있다는 부분에서 장점.
  명령 중간에 커맨드 명령 등 다양하게 실행이 가능하다고 하더라구요.
  가상환경을 만들어주는 방법이 있는지 모르겠습니다.
- VS Code
  다양한 Extention 지원으로 커스텀하기 좋습니다.
  필요시 가상환경을 따로 만들어 줘야해서 번거로움이 있습니다.
  
  > VS Code에 파이썬 파일 Fira Code (폰트) 적용.
  > `ctrl`+`shift`+`p` 후  settings.json 검색해 들어감.
  >
  > ```
  > "[python]": {
  >      "editor.fontFamily":"Fira Code",
  >      "editor.fontLigatures": true,
  >  },
  > ```
  > 추가하면 설정 됨.
  > 위와 같은 방법으로 템사이즈 등 다양한 적용이 가능.



## 0.3. 가상환경 만들기.

독립된 환경에서 개발하기 위한 방법으로 가상환경을 씁니다.
Python 가상환경은 만들 수 있는 모듈이 여러가지 있습니다.

- 가상환경을 사용하는 이유.
  - 패키지 호환 문제.(여러개 프로젝트를 개발할 경우 충돌가능성이 있음.)
  - 버전문제. (모듈, python 상황에 따라 모듈이나 패키지의 버전을 사용하는 경우.)

- python 가상환경 종류.
  - **venv** : Python3.4부터 표준배포판에 탑재. (대충 설치가 필요 없다는 말)
  - **virtualenv** : pip로설치. Python 2.6 부터 쓰임.
  - **pyenv** : conda, venv가 잘격리 되지 않는다고 합니다.
  - **conda** : pyenv가 아닌 환경에서만 유효하다고 합니다. 가상환경만을 구성하는 모듈은 아님. pip로 설치.

<h4>-venv로 가상환경 만들기.</h4>
1. 가상환경 만들기. 
명령창에서 `python -m venv 가상환경이름`
ex) `python -m venv example-venv`
2. 가상환경 활성화.
  - window
명령창에서 `source 가상환경이름/Scripts/activate`
ex) `source example-venv/Scripts/activate`
  - MAC
명령창에서 `source 가상환경이름/bin/activate`
ex) `source example-venv/bin/activate`

4. 3. 가상환경 비활성화
    `deactivate`
4. 패키지 목록 가져오기.
   `pip freeze > requirements.txt`  -> 일부러 requirements.txt로 쓴다고 하니 지켜주세요.
5. 패키지 목록 설치.
   `pip install -r requirements.txt`
6. 패키지 목록 삭제.
   `pip uninstall -r requirements.txt`

> - 가상환경 폴더를 다른 곳으로 이동한 경우.
>    activate.bat, Activate.ps1, activate 파일 안의 VIRTUAL_ENV 부분을 이동 시킨 폴더 경로로 수정.



## 0.4. 용어 설명

- 리터럴
  변하지 않고 고정된 데이터.
- 표현식
  값을 표현하는 방식.
- 파이썬 쉘
  IDLE의 모드 중 하나. 자동완성 등 편의 기능을 제공함.



# 1. Python 연산자와 자료형, 주소의 개념과 이해.

사용에 필요한 기본적인 내용과 이론.



## 1.0. 기본 연산자.

- 기본 연산자
  더하기 : +
  빼기 : -
  곱하기 : *
  나누기 : / (float형 자료)
  몫 : // (int형 자료)
  나머지 : %
  제곱 : **

- 비교 연산자
  \> : 초과 미만 비교
  < : 초과 미만 비교
  \>= : 이상 이하 비교
  \<= : 이상 이하 비교
  == : 같으면 True
  != : 다르면 True
- 논리 연산자
  or : or 연산자, 좌항이 0이 아니면 좌항 선택. 좌항이 0이면 우항 선택.
  and : and 연산자, 좌항이 0이 아니면 우항 선택. 좌항이 0이면 좌항(0)선택.
  in : 포함관계 연산자
  not : - 부호 연산자 처럼 작동.
- 쉬프트 연산자
  \>>K : 쉬프트 연산자 데이터 범위를 넘어가면 사라짐. (계산된 값은 2^K 나누고 정수만 가진 값.)
  \<<K : 쉬프트 연산자 데이터 범위를 넘어간 부분은 0으로 처리됨. (계산된 값은 2^K 곱하고 정수만 가진 값.)
- 비트 연산자
  & : and bit 연산자
  | : or bit 연산자
  ^ : xor bit 연산자. 같으면 1or True, 다르면 0 or False
  ~ : not bit 연산자. 주어진 데이터 비트를 반전.

```python
>>> a=123143183413412341234
>>> a<<2
492572733653649364936
>>> a<<1
246286366826824682468
>>> a>>1
61571591706706170617
>>> a>>2
30785795853353085308
>>> a>>15
3758031720380015
>>> a>>50
109373
```

2진수 : 0b@@@ (@@@는 0~1로 이루어진 숫자.)
8진수 : 0o@@@ (@@@는 0~7로 이루어진 숫자.)
16진수 : 0x@@@ (@@@는 0~9, a, b, c, d, e, f로 이루어진 숫자.)

앞에 `#`을 입력하면 추석처리 됨.



## 1.1. 숫자

```python
>>> # 2진수 str만들기 결과에 나온 숫자를 직접 타이핑 해도 됨.
>>> bin(42)
'0b101010'
>>> bin(0b101010)
'0b101010'
>>> # 8진수 str만들기
>>> oct(42)
'0o52'
>>> oct(0b101010)
'0o52'
>>> # 16진수 str만들기
>>> hex(42)
'0x2a'
>>> hex(0b101010)
'0x2a'
>>> # 10진수
>>> str(0b101010)
'42'
>>> 
>>> 
>>> # 문자열을 다른 진수의 숫자로 바꾸기.
>>> int('0b101010', 2)
42
>>> int('0o52', 8)
42
>>> int('0x2a', 16)
>>>
>>>
>>> # 접두어 제외.
>>> format(42, 'b')
'101010'
>>> format(42, 'o')
'52'
>>> format(42, 'x')
'2a'
>>> format(42, 'X')
'2A'
>>> format(42, 'd')
'42'
>>> # 접두어 포함.
>>> format(42, '#b')
'0b101010'
>>> format(42, '#o')
'0o52'
>>> format(42, '#x')
'0x2a'
>>> format(42, '#X')
'0X2A'

```





## 1.2. 자료형. 내장 자료형.

 자료형은 잘 확인해주어야 합니다. 선언시에 자료형을 주기 않고, 변수의 값을 바꿀 때도 자료형에 상관없이 받기 때문에 주의가 필요합니다. (자료형이 달라서 결과가 나오지않는 경우가 있습니다.)

- 숫자
  int : 정수(무한대 값이 입력가능하답니다.)
  float : 실수
  bool : 참, 거짓
  complex : 복소수 (7+6j)
- 시퀀스
  str : 문자열
  list : 리스트
  tuple : 튜플
- 셋
  set : 셋, 집합
- 매핑
  dict : 딕셔너리



### 1.2.1. 문자열(str)



#### 1.2.1.1. 문자열(str) 다루기.

큰 따옴표와 작은 따옴표 모두 같은 결과로 가져옴. 
escape할 때는 `\'` , `\"`로 쓰면 됨.
`'''`, `"""`는 여러줄의 문자열 리터럴(값)을 만들 때 사용.

문자열 자료형에 +,* t사용 가능.

- 문자열 슬라이싱.
  
  ```python
  >>> word = 'Python'
  'Python'
  >>> print(word[0])
  'P'
  >>> print(word[3])
  'h'
  >>> print(word[-1])
  'n'
  >>> print(word[-3])
  'h'
  >>> print(word[2:])
  'thon'
  >>> print(word[0:2])
  'Py'
  >>> print(word[0:4])
  'Pyth'
  >>> print(word[:5])
  'Pytho'
  ```
- 왼쪽 정렬

  ```python
  >>> "{0:<10}".format("hi")
  'hi        '
  ```

- 오른쪽 정렬

  ```python
  >>> "{0:>10}".format("hi")
  '        hi'
  ```

- 가운데 정렬

  ```python
  >>> "{0:^10}".format("hi")
  '    hi    '
  ```

- 공백 채우기

  ```python
  >>> "{0:=^10}".format("hi")
  '====hi===='
  >>> "{0:!<10}".format("hi")
  'hi!!!!!!!!'
  ```

- 소수점 표현

  ```python
  >>> y = 3.42134234
  >>> "{0:0.4f}".format(y)
  '3.4213'
  >>> "{0:10.4f}".format(y)
  '    3.4213'
  ```

- f 문자열 포매팅 (Python 3.6버전 이상 지원하는 기능.)

  ```python
  >>> name = '홍길동'
  >>> age = 30
  >>> f'나의 이름은 {name}입니다. 나이는 {age-5}입니다.'
  '나의 이름은 홍길동입니다. 나이는 25입니다.'
  ```

  ```python
  >>> d = {'name':'홍길동', 'age':30} # 딕셔너리
  >>> f'나의 이름은 {d["name"]}입니다. 나이는 {d["age"]}입니다.'
  '나의 이름은 홍길동입니다. 나이는 30입니다.'
  ```

  ```python
  >>> f'{"hi":<10}'  # 왼쪽 정렬
  'hi        '
  >>> f'{"hi":>10}'  # 오른쪽 정렬
  '        hi'
  >>> f'{"hi":^10}'  # 가운데 정렬
  '    hi    '
  ```

  ```python
  >>> f'{"hi":=^10}'  # 가운데 정렬하고 '=' 문자로 공백 채우기
  '====hi===='
  >>> f'{"hi":!<10}'  # 왼쪽 정렬하고 '!' 문자로 공백 채우기
  'hi!!!!!!!!'
  ```

  ```python
  >>> y = 3.42134234
  >>> f'{y:0.4f}'  # 소수점 4자리까지만 표현
  '3.4213'
  >>> f'{y:10.4f}'  # 소수점 4자리까지 표현하고 총 자리수를 10으로 맞춤
  '    3.4213'
  ```

  ```python
  >>> f'{{ and }}' # {} 표시방법
  '{ and }'
  ```

- 문자열 삽입

  ```python
  >>> ",".join(['a', 'b', 'c', 'd'])
  'a,b,c,d'
  ```

  


#### 1.2.1.2. str 메서드

| 메서드                                    | 설명                                                         |
| ----------------------------------------- | ------------------------------------------------------------ |
| capitalize()                              | 첫 문자가 대문자, 나머지 소문자 변환                         |
| casefold()                                | 케이스 폴딩 된 문자열 반환. (소문자로 바꿉니다.)             |
| center(*width*[, *fillchar*])             | 길이 width 인 문자열의 가운데에 정렬한 값을 반환.            |
| count(*sub*[, *start*[, *end*]])          | sub(str)이 중첩되지 않고 등장한 횟수.<br />start, end는 슬라이스 |
| find(*sub*[, *start*[, *end*]])           | sub(str)인 첫 번째 인덱스 반환. 없으면 -1                    |
| index(sub)                                | sub(str)인 첫 번째 인덱스 반환. 없으면 ValueError            |
| encode(encoding="utf-8", errors="strict") | 문자열의 바이트열 객체로 인코딩된 버전을 돌려줌.<br />errors는 인코딩 오류시 처리방법<br />(codecs.register_error()를 통해 등록된 이름이 값.)<br /> - strict : UncodeError 발생<br /> - ignore : 무시<br /> - replace : <br /> -xmlcharrefreplace<br /> -backslashreplace |
| endswith(*suffix*[, *start*[, *end*]])    | suffix(str 혹은 튜플)로 끝나면 True, 아니면 False<br />다른 옵션은 슬라이스. |
| format(*\*args*, *\*\*kwargs*)            | 문자열 포맷 연산을 수행.<br />문자열에 변수를 넣어 str로 만들어줌..<br />Ex1) `"I ate {number} apples. so I was sick for {day} days.".format(number=10, day=3)`<br />Ex2)`"I ate {0} apples. so I was sick for {1} days.".format(number, day)` |
| upper()                                   | 대문자 변환.                                                 |
| lower()                                   | 소문자 변환.                                                 |
| lstrip<br />rstrip<br />strip             | 공백 지우기.                                                 |
| replace(before, after)                    | 문자열 일부분 바꾸기.                                        |
| split(lim=" ")                            | lim(str)으로 구분해서 리스트로 반환.                         |



### 1.2.2. bool(참거짓)

| 값        | 참 or 거짓 |
| :-------- | :--------- |
| "python"  | 참         |
| ""        | 거짓       |
| [1, 2, 3] | 참         |
| []        | 거짓       |
| ()        | 거짓       |
| {}        | 거짓       |
| 1         | 참         |
| 0         | 거짓       |
| None      | 거짓       |



### 1.2.3. 리스트.

다른 프로그래밍 언어에서 말하는 리스트와 개념적으로 다름.

#### 1.2.3.1. 리스트 생성.

- 비어있는 리스트 생성 방법 2가지.

  ```python
  >>> a=list()
  >>> a=[]
  ```

- 리스트 생성 방법 1

  ```python
  odd = [1, 3, 5, 7, 9]
  ```

- 리스트 생성 방법 2

  ```python
  range()
  ```



#### 1.2.3.2. 리스트 다루기.

- 슬라이싱

  ```python
  >>> a=[5,3,1]
  >>> a
  [5, 3, 1]
  >>> a[0]
  5
  >>> a[1]+a[0]
  8
  >>> a[-1]
  1
  >>> b=[1, 2, 3, ['a', 'b', 'c']]
  >>> b[3]
  ['a', 'b', 'c']
  >>> b[3][2]
  'c'
  >>> b[3][0]
  'a'
  >>> a = [1, 2, 3, 4, 5]
  >>> a[0:2]
  [1, 2]
  >>> b = a[:2]
  >>> c = a[2:]
  >>> b
  [1, 2]
  >>> c
  [3, 4, 5]
  ```

- 리스트 연산

  ```python
  >>> a = [1, 2, 3]
  >>> b = [4, 5, 6]
  >>> a + b
  [1, 2, 3, 4, 5, 6]
  ```

- 리스트 반복(* 연산)

  ```python
  >>> a = [1, 2, 3]
  >>> a * 3
  [1, 2, 3, 1, 2, 3, 1, 2, 3]
  ```

- 리스트 길이 구하기

  ```python
  >>> a = [1, 2, 3]
  >>> len(a)
  3
  ```

- 값 수정

  ```python
  >>> a = [1, 2, 3]
  >>> a[2] = 4
  >>> a
  [1, 2, 4]
  ```

- 값 삭제

  ```python
  >>> a = [1, 2, 3]
  >>> del a[1]
  >>> a
  [1, 3]
  >>> a = [1, 2, 3, 4, 5]
  >>> del a[2:]
  >>> a
  [1, 2]
  ```

  > Python에서는 del 객체가 존재한다.



#### 1.2.3.3. 리스트 메서드.

| 메서드               | 설명                                                         |
| -------------------- | ------------------------------------------------------------ |
| append(value)        | list 뒤에 value 값 추가.                                     |
| sort()               | 순서대로 정렬.                                               |
| reverse()            | 순서를 반대로 바꿈.                                          |
| index(value)         | value와 같은 값을 가지는 요소가 있으면  첫 번째 인덱스 반환<br />없으면 ValueError |
| insert(index, value) | index에 value를 넣고 원래의 요소들은 1개씩 순서가 밀림.      |
| remove(value)        | value와 같은 값을 가지는 요소가 있으면  첫 번째 요소 제거<br />없으면 ValueError |
| pop(index = -1)      | index의 요소를 반환하고 삭제. index를 주지 않으면 마지막 요소. |
| count(value)         | value와 같은 갯수 카운트.                                    |
| extend(valueslist)   | 리스트의 뒤에 valueslist의 요소를 추가하여 연장시킴.(더하기 연산과 동일) |



### 1.2.4. 튜플

튜플이 리스트와 다른 점.
   - 튜플은 ()를 사용.
   - 값의 생성, 삭제, 수정이 불가능.



#### 1.2.4.1. 튜플 다루기.

- 인덱싱, 슬라이싱, 더하기, 곱하기

  ```python
  >>> t1 = (1, 2, 'a', 'b')
  >>> t1[0]
  1
  >>> t1[3]
  'b'
  >>> t1[1:]
  (2, 'a', 'b')
  >>> t1 = (1, 2, 'a', 'b')
  >>> t2 = (3, 4)
  >>> t1 + t2
  (1, 2, 'a', 'b', 3, 4)
  >>> t2 = (3, 4)
  >>> t2 * 3
  (3, 4, 3, 4, 3, 4)
  ```

- 튜플 길이 구하기

  ```python
  >>> t1 = (1, 2, 'a', 'b')
  >>> len(t1)
  4
  ```



### 1.2.5. 딕셔너리

구조는 JSON 구조와 같다. JSON으로 값을 바꾸거나 JSON으로 바꾸는 것이 가능하다.
Key와 Value가 쌍을 이루고 있다. Key를 통해서 Value를 찾거나 Value를 통해서 Key를 찾을 수 있다.

Key는 반드시 고유한 값이어야 한다. Value는 str, list 등으로 구성해도 된다.

#### 1.2.5.1. 딕셔너리 다루기.

- 딕셔너리 생성, 추가, 삭제.

  ```python
  >>> dic = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
  
  >>> a = {1: 'a'}
  >>> a[2] = 'b'
  >>> a
  {1: 'a', 2: 'b'}
  >>> a['name'] = 'pey'
  >>> a
  {1: 'a', 2: 'b', 'name': 'pey'}
  
  >>> del a[1]
  >>> a
  {2: 'b', 'name': 'pey', 3: [1, 2, 3]}
  ```

  > dic이름[key]를 통해서 해당 key의 value를 얻는다.
  > 만일 이 방법으로 존재하지 않는 key를 쓸 경우 ValueError 발생.

- 값이 들었는지 확인.

  ```python
  >>> a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
  >>> 'name' in a
  True
  >>> 'email' in a
False
  ```
  
- 주의사항

  ```python
  >>> a = {1:'a', 1:'b'}
  >>> a
  {1: 'b'}
  ```

  > key는 고유값이어야 하기 때문에 뒤에 제시된 것이 남는다.



#### 1.2.5.2. 딕셔너리 메서드.

| 메서드   | 설명                                                         |
| -------- | ------------------------------------------------------------ |
| keys()   | 딕셔너리 Key로 이루어진 dict_keys 반환.<br />for문에 사용가능. list 메서드 사용 불가.<br />(메모리 낭비를 줄이기 위해 사용하는 형태.)<br />list(a.keys())로 리스트로 만들 수 있음. |
| Values() | 딕셔너리 Key로 이루어진 dict_values 반환.<br />for문에 사용가능. list 메서드 사용 불가.<br />(메모리 낭비를 줄이기 위해 사용하는 형태.)<br />list(a.values())로 리스트로 만들 수 있음. |
| items()  | Key, Value 쌍을 얻음. dic_items 객체.<br />Key와 Value를 튜플로 묶음. |
| clear()  | Key, Value 모두 지움.                                        |
| get(key) | key에 해당하는 Value를 얻음.<br />없으면 None을 반환한다는 점에서 a[key]와 다르다. |
|          |                                                              |



#### 1.2.5.3. Json과 Dic 다루기.

```python
import json

ex_json='''{
    "json_string" : "string_example_for_json",
    "json_number" : 100,
    "json_array" : [5, 4, 3, 2, 1],
    "json_object" : { "name_json":"john", "age_json":30},
    "json_bool" : true
}
'''

ex_dic={
    "dic_string" : "string_example_for_dic",
    "dic_number" : -100,
    "dic_array" : [-5, -4, -3, -2, -1], 
    "dic_object" : {"name_dic":"JOHN", "age_dic":-30},
    "dic_bool" : False
}

# dic을 json문자열로 파싱. 내부의 자료도 list, dic, int, boolean 형태로 맞게 변화
json_from_dic = json.dumps(ex_dic)
# json 문자열을 dic으로 파싱.
dic_from_json = json.loads(ex_json)

print(json_from_dic)
print("//////////////////////////////////")
print(dic_from_json)
print("==================================")
print(json_from_dic[7:20])

print(type(json_from_dic))
print("==================================")
print("----------------------------------")
print(dic_from_json["json_array"])
print(dic_from_json["json_array"][2])

print(dic_from_json["json_object"])
print(dic_from_json["json_object"]["name_json"])
print("----------------------------------")

"""   결과
{"dic_string": "string_example_for_dic", "dic_number": -100, "dic_array": [-5, -4, -3, -2, -1], "dic_object": {"name_dic": "JOHN", "age_dic": -30}, "dic_bool": false}
//////////////////////////////////
{'json_string': 'string_example_for_json', 'json_number': 100, 'json_array': [5, 4, 3, 2, 1], 'json_object': {'name_json': 'john', 'age_json': 30}, 'json_bool': True}   
==================================
tring": "stri
<class 'str'>
==================================
----------------------------------
[5, 4, 3, 2, 1]
3
{'name_json': 'john', 'age_json': 30}
john
----------------------------------
"""
```

> dic을 json문자열로 파싱. 내부의 자료도 list, dic, int, boolean 형태로 맞게 변화
>
> - json_from_dic = json.dumps(ex_dic)
>
> json 문자열을 dic으로 파싱.
>
> - dic_from_json = json.loads(ex_json)



### 1.2.6. 집합자료형 (set)

주로 캐스팅을 통해서 만들어 줌. 중학교 때 배운 그 집합의 개념.

- 특징
  - 중복 불가. (중복 필터로 사용 가능.)
  - 순서 없음.



#### 1.2.6.1. 집합 자료형 다루기.

- set 생성(list와 str)

  ```pyt
  >>> s1 = set([1,2,3])
  >>> s1
  {1, 2, 3}
  
  >>> s2 = set("Hello")
  >>> s2
  {'e', 'H', 'l', 'o'}
  ```

- 교집합, 합집합, 차집합

  ```python
  >>> s1 = set([1, 2, 3, 4, 5, 6])
  >>> s2 = set([4, 5, 6, 7, 8, 9])
  >>> # 교집합   s2.intersection(s1) 와 같음.
  >>> s1 & s2
  {4, 5, 6}
  >>> # 합집합   s2.union(s1) 와 같음.
  >>> s1.intersection(s2)
  {4, 5, 6}
  >>> # 차집합 1
  >>> s1 | s2
  {1, 2, 3, 4, 5, 6, 7, 8, 9}
  >>> # 차집합 2
  >>> s1.difference(s2)
  {1, 2, 3}
  >>> s2.difference(s1)
  {8, 9, 7}
  ```

#### 1.2.6.2. 집합 자료 관련 메서드

| 메서드                      | 설명                                   |
| --------------------------- | -------------------------------------- |
| intersection(valuesSet)     | valuesSet과 교집합.                    |
| union(valuesSet)            | valuesSet과 합집합.                    |
| difference(valuesSet)       | set에서 valuesSet의 요소를 뺀 차집합.  |
| add(value)                  | set에 value의 요소 추가.               |
| update(valuesList)          | set에 valuesList의 요소 추가.          |
| remove(value or valuesList) | set에서 value or valuesList 요소 제거. |



## 1.3. 주소의 개념과 이해. (얕은 복사와 깊은 복사)

컴퓨터에서 메모리는 크게 스택(Stack), 힙(Heap), 데이터(Data) 세가지로 구분된다.
Python 코드를 이해하기 위해서는 3개의 용도와 개념에 대해 이해하고, Python에서는 어떤 식으로 작동하는지 이해할 필요가 있다.

| 메모리 공간 이름 | 저장되는 내용              | 설명                                                         |
| ---------------- | -------------------------- | ------------------------------------------------------------ |
| Data             | 전역변수, Static 변수      | 시작과 동시에 할당.<br />프로그램이 종료되어야 메모리에서 소멸. |
| Heap             | 프로그래머가 할당하는 변수 | 동적으로 메모리를 할당 할 때 사용.<br />파이썬에서는 모든 값이 여기에 저장됨.(동적 할당) |
| Stack            | 지역변수, 배개변수         | 함수 호출 시 생성, 완료시 사라짐.<br />지역변수와 매개 변수가 저장.<br />상황에 따라 값은 Heap에 저장하고,<br />Stack에는 주소가 저장됨. (Heap의 주소)<br />파이썬에서는 모든 자료는 주소만 가지고 있음. |

C언어의 경우 3개의 영역을 조절해가면서 변수나 데이터를 할당 할 수 있다. (Python에서 C언어 설명은 그만.)
하지만 Python의 경우 모든 데이터는 Heap에 저장되고 Stack에는 주소만 가지고 있다. 실제 주소를 알아보는 방법은 아래와 같다.

- 얕은 복사 예제. (주소만 복사)
  ```python
  >>> a=[1,2,3]
  >>> id(a)
  2726376264776 # 값은 실행할 때마다 다를 수 있다. a의 값이 저장된 메모리 주소.
  >>> b=a
  >>> id(b)
  2726376264776 # b는 a의 주소를 복사해 왔다.
  >>> a[1]=5 # a의 값을 변화.
  >>> a
[1, 5, 3] # a의 값 확인.
  >>> b
  [1, 5, 3] # b의 값 확인.
  >>> a is b  # a와 b가 가리키는 객체는 동일한가?
True
  ```
  
  > 위의 예를 들었듯이 a의 값을 바꾸었지만 b의 값도 함께 바뀌었다. b와 a에 저장된 Heap의 주소가 같아서가리키는 값이 같기 때문이다.
  > 따라서 Heap에 있는 값을 하나만 바꾸어도 값이 같이 바뀐다.

- 깊은 복사 예제. (주소에 있는 값을 복사)

  ```python
  >>> a = [3,2,1]
  >>> b = [3,2,1]
  >>> a is b
  False
  >>> c = a
  >>> a is c
  True
  >>> d=[]
  >>> for i in a:d.append(i)
  >>> d
  [3, 2, 1]
  >>> a is d
  False
  ```

  > 위 결과를 보면 값이 같음에도 불구하고 a is b 와 a is c 에서 False가 나온다.

- 깊은 복사를 하는 방법 1 - 슬라이싱 

  ```python
  >>> a = [1, 2, 3]
  >>> b = a[:]
  >>> a is b
  False
  >>> a[1] = 4
  >>> a
  [1, 4, 3]
  >>> b
  [1, 2, 3]
  ```

- 깊은 복사를 하는 방법 2 - 카피 모듈

  ```python
  >>> from copy import copy
  >>> a = [1, 2, 3]
  >>> b = a[:]
  >>> b = copy(a)
  >>> a is b
  False
  ```


## 1.4. 변수 다루기.
- 파이썬에서는 한번에 여러개의 변수를 선언하는 방법도 있다.
  ```python
  # 튜플을 이용한 변수 선언 1.
  >>> (a, b) = 'python', 'life'
  
  # 튜플을 이용한 변수 선언 2.
  >>> [a,b] = ['python', 'life']
  
  # 여러개의 변수에 같은 값을 넣는 방법.
  >>> a = b = 'python'
  
  # 변수의 값을 바꾸는 방법.
  >>> a = 3
  >>> b = 5
  >>> a, b = b, a
  >>> a
  5
  >>> b
  3
  ```



# 2. Python 제어문.

if, while, for 문에 대해 배웁니다.



## 2.1. 파이썬의 작성 요령.

python은 C/C++, Java와 달리 제어문의 사용에서 괄호()를 이용하지 않는다.
콜론(:)을 이용해서 조건문과 실행문을 구분.
실행문은 띄어쓰기 네번으로 어디까지가 제어문에 포함된 실행되는지 구분.
제어문 전체가 끝나면 들여쓰기(띄어쓰기 네번)을 지우고 시작.
switch - case 문이 없다. (비슷하게 쓰는 걸 알려드립니다.)



### 2.2. if 문.

```python
if 조건문:
    수행할 문장1
    수행할 문장2
    수행할 문장3
    ...
elif 조건문2:
    수행할 문장4
    수행할 문장5
    수행할 문장6
    ...
... # 다음 조건문 0개~여러개 붙여도 된다.
else :
    수행할 문장7
    수행할 문장8
    수행할 문장9
    ... # else
```

```python
표현식 if 조건식 else 표현식
표현식 if 조건식 else 조건표현식 if 조건식 else 조건표현식
```



## 2.3. 반복문 for.

python 에서는 iterable한 객체 라는 개념이 있다. for문은 이 iterable객체를 이용하여 반복문을 실행한다.

- iterable객체
  str : 1 글자씩.
  list, set : 1개 요소 씩.
  dict : 1쌍의 key, value 씩.
  range : 1개 요소 씩.

```python
for i in [1,2,3,74,2,7]:
    실행문
# list 객체에서 순서대로 하나씩 i의 값이 되어 실행문에서 사용이 가능하다.
```

```python
for i in range(0,10):
    print(i)
'''
0
1
2
3
4
5
6
7
8
9
'''
```



### 2.3.1. range 함수.

python 의 range함수는 range라는 객체를 생성하는 함수이다. range 또한 iterable한 객체로 for문에서 원하는 횟수 만큼 반복 할 때 많이 사용한다.

| range 함수         | 사용 결과                                                    |
| ------------------ | ------------------------------------------------------------ |
| range(num)         | 0부터 num-1 까지의 숫자를 가진 range 객체                    |
| range(n1, n2)      | n1부터 n2 - 1 까지의 숫자를 가진 range 객체                  |
| rnage(n1, n2, gab) | n1부터 gab 씩 더해진 숫자  중 n2 보다는 작은 수를 가진 range 객체 |



### 2.3.2. break 문.

break 문은 실행 시 해당 for문(혹은 while 문을 빠져 나간다.)

```python
coins=[5,5,5,2,1,2,1,3,4,6,62]
for coin in coins:
    if coin==1:
        print('1짜리!!!.')
        break
    else:
        print('1짜리 아님.')
# 결과
'''
1짜리 아님.
1짜리 아님.
1짜리 아님.
1짜리 아님.
1짜리!!!.
'''
```



### 2.3.3. continue 문.

continue 문은 항목(요소)의 연산을 건너뛴다.

```python
coins=[5,5,5,2,1,2,1,3,4,6,62]
for coin in coins:
    if coin==1:
        print('1짜리!!!.')
        continue
        print('1짜리2222!!!.')
    else:
        print('1짜리 아님.')
'''
1짜리 아님.
1짜리 아님.
1짜리 아님.
1짜리 아님.
1짜리!!!.
1짜리 아님.
1짜리!!!.
1짜리 아님.
1짜리 아님.
1짜리 아님.
1짜리 아님.
'''
```



### 2.3.4. for else 문.

```python
for c in 'python':
    print(c)
else :
    print('finish!!')
'''
p
y
t
h
o
n
finish!!
'''
```



### 2.3.5. 리트스 내포 확장. [expr for x in iterable객체 if 조건식]

```python
>>> [x for x in range(1,10) if x%2==0]
[2, 4, 6, 8]
>>> [x**3 for x in range(1,10) if x%2==0]
[8, 64, 216, 512]
>>> ['짝' if x%2==0 else '홀']
```



## 2.4. while 문.

```python
while 조건문:
    실행문
# 조건문이 True일 때 실행문이 실행된다. 설정하기에 따라 무한으로 반복 가능.
```



# 3. Python 함수.

반복적으로 행해려는 일련의 과정들을 묶어서 하나의 과정으로 만들었다고 생각하면 쉽다.



## 3.1. Python 함수 기초.

### 3.1.1. 기본적인 함수 정의 방법.

- Python에서 함수를 정의 하는 방법

  ```python
  '''
  def 함수이름(형식인수(parameter)....):
      실행문
  '''
  def func1(x,y):
      print(x,y)
  ```

- 기본값 주워주기 (default값 지정.)

  ```python
  def func1(x,y=10):
      print(x,y)
  ```

  > 함수를 사용 할 때, y의 값을 생략하면 y를 10으로 계산함. 
  > **기본값이 주워진 경우 반드시 다른 파라미터보다 오른쪽에 정의 되어야 함.**


### 3.1.2. 기본적인 함수 사용 방법.

- Python함수 사용법 - 순서대로(위치인수)

  ```python
  def func1(year, month, day):
      print(f'{year}년 {month}월 {day}일')
  
  func1(100,10000,20000)
  '''결과
  100년 10000월 20000일
  '''
  ```

- Python함수 사용법 - 인자의 이름에 따라 정의(키워드인수)

  ```python
  def func1(year, month, day):
      print(f'{year}년 {month}월 {day}일')
  
  func1(day=100,year=10000,month=20000)
  '''결과
  100년 10000월 20000일
  '''
  ```
  
- 기본값이 주워진 경우.

  ```python
  def func1(year, month, day=1):
      print(f'{year}년 {month}월 {day}일')
  
  func1(year=10000,month=20000)
  func1(100,20000)
  '''결과
  10000년 20000월 1일
  100년 20000월 1일
  '''
  ```

## 3.2. 가변인수를 받는 함수. (인수의 개수가 미정인 경우)

함수에 전달할 인수의 개수가 미정인 상태인 인수(argument)를 넣을 경우.
parameter에 '\*'와 '\*\*'를 이용해서 만들 수 있다.
'\*'는 튜플 형태로 전달.
'\*\*'는 함수내부에서 dict 형식으로 사용한다. 
단, 다른 인자를 포함하여 정의 할 경우에는 '\*', '\*\*' 가 붙은 경우 뒤쪽으로 두어야 한다. (앞쪽에 두면 에러 발생)

- 가변인수인 함수 정의 - 튜플.

  ```python
  def argsfunc(*args):
      i=0
      for x in args:
          i+=1
      print("인수의 갯수 : %d" % i)
      print(args)
  
  argsfunc(1,2,(3,4,5))
  
  print("======")
  
  argsfunc(1,[7,55],"test", {'a':1, 'b':100})
  
  
  '''결과
  인수의 갯수 : 3
  (1, 2, (3, 4, 5))
  ======
  인수의 갯수 : 4
  (1, [7, 55], 'test', {'a': 1, 'b': 100})
  '''
  ```

- 가변인수인 함수 정의 - dict.

  ```python
  def dictfunc(**dicts):
      i=0
      for x in dicts.keys():
          i+=1
          print(f'{x} - {dicts.get(x)}')
      print("인수 개수 : %d" % i)
      print(dicts)
  
  dictfunc(a=1, b=3, c=7)
  
  
  '''결과
  a - 1
  b - 3
  c - 7
  인수 개수 : 3
  {'a': 1, 'b': 3, 'c': 7}
  '''
  ```



## 3.3. 반환 return.

함수는 반드시 되돌려주는 값이 있다. 정의하지 않으면 None을 반환한다.


1. 정의하지 않으면 None 반환
2. **다른 값을 정의**하고, **함수를 종료**하는 기능으로 **return**을 사용한다.
   (함수 안에서 return 다음에 쓴 내용은 실행되지 않는다.)
3. 반환하는 값은 반드시 1개이다.
   다만 ","를 이용할 경우 튜플로 묶어 1개의 튜플에 여러개의 결과를 반환가능하다.



## 3.4. 영역과 이름 공간.

함수의 내부와 외부는 분리된 공간으로 생각해야 한다.



### 3.4.1. 전역 영역과 지역 영역.

1. 함수 내부에서 정의한 값은 외부에서 사용이 불가능하다.
2. 함수 내부에서 외부의 숫자를 변경은 global변수(전역변수)만 가능하다.
   \*global변수는 실행되고 있는 영역 전체에서 사용가능한 변수를 뜻한다.
   단, 일반 변수도 정의된 값이 있다면 사용은 가능하다.

| 특징             | 전역변수<br />(함수 밖, 전역 이름 공간에서 정의) | 지역변수<br />(함수 안, 지역 이름 공간에서 정의) |
| ---------------- | ------------------------------------------------ | ------------------------------------------------ |
| 함수 안에서 읽기 | 가능                                             | 가능                                             |
| 함수 안에서 수정 | 불가(단, global 키워드 사용시 가능.)             | 가능                                             |
| 함수 밖에서 읽기 | 가능                                             | 불가능                                           |
| 함수 밖에서 수정 | 가능                                             | 불가능                                           |

- global 키워드 사용 방법.

  ```python
  a = 1
  
  def normaltest(z):
      a = z + 2
      return a
  
  b = normaltest(3)
  print(a)
  print(b)
  
  def globaltest(z):
      global a
      a = z + 4
      return a
  
  c = globaltest(5)
  print(a)
  print(c)
  
  print("==================")
  print(locals())
  
  '''결과
  1
  5
  9
  9
  ==================
  {'__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <_frozen_importlib_external.SourceFileLoader object at 0x0000023FBDDAE048>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, '__file__': '1.py', '__cached__': None, 'a': 9, 'normaltest': <function normaltest at 0x0000023FBDD93948>, 'b': 5, 'globaltest': <function globaltest at 0x0000023FBDDB19D8>, 'c': 9}
  '''
  ```

  **locals()**
  
  >각 영역의 이름공간을 dict형식으로 반환한다. 수정도 가능하다. 다만 프로그램은 이 영역에서 값을 사용하기 때문에 결과가 바뀔 수 있으니 주의.
  >
  >- '\_\_name\_\_':'\_\_main\_\_'
  >  해당 프로그램이 직접 호출되었음을 의미한다. 만약 외부에서 불러온 경우(패키지나 모듈로써 가져온 경우)해당 이름으로 나타난다. 패키지와 모듈에서 더 상세히 다룸.
  >- '\_\_file\_\_':'1.py'
  >  실행시킨 파일의 이름.
  >- '\_\_builtins\_\_'
  >  파이썬에 내장된 코드 집합. 모든 파이썬 프로그램은 시작과 동시에 builtins의 내부를 참조 할 수 있도록 처리됨.
  >- 그 외에 캐쉬, 영역에서 지정한 변수명에 대한 값과 메모리 주소, 패키지, 등 다양한 정보가 나타난다.



### 3.4.2. 내장 함수와 내장 영역.

 여지껏 정의하지 않고 사용한 함수들은 전부 내장 영역에 들어있는 내장 함수에서 온 것이다.
내장영역은 '\_\_builtins\_\_'에 있으며, 파이썬 프로그램은 시작과 동시에 builtins의 내부를 참조하도록 되어 내장 함수가 사용이 가능한 것이다.



### 3.4.3. Python 스코핑룰.

지역, 전역, 내장 영역은 서로 계층적으로 분리된 영역.
스코핑룰은 여기서 하나의 영역에서 다른 영역의 변수를 참조할 때 따르는 규칙.

|           |      |                |
| --------- | ---- | -------------- |
| 내장 영역 | ▶    | 내장 이름 공간 |
|           |      | ▲              |
| 전역 영역 | ▶    | 전역 이름 공간 |
|           |      | ▲              |
| 지역 영역 | ▶    | 지역 이름 공간 |

위 표와 같이 없으면 찾아가는 영역.
지역 영역에서 지역 이름 공간을 먼저 찾고, 없으면 전역 이름 공간, 거기서도 없으면 내장 이름 공간을 찾음.



## 3.5. 람다 표현식.

함수는 각각 이름과 실행할 내용을 정의하지만 람다식은 이름을 정의하지 않음. 이름이 없기에 익명함수라 함. 표현 식은 `lambda 인수 : 표현식` 을 기본으로 함. 다른 명령을 주지 않아도 결과값을 반환.

- 람다식 정의

  ```python
  >>> (lambda x : x**2)(2)
  9
  ```

- 람다식에 이름 주기

  ```python
  >>> lambda_func = lambda x : x**2
  >>> lambda_func(3)
  9
  ```

- 람다식 응용 - 콜백함수

  ```python
  li = [9,1,7,3,4,2,5,6,8]
  
  # 오름차순 정렬 li의 각 요소를 x로 보고, x 순서로 오름차순 정렬
  li.sort(key=lambda x: x)
  print(li)
  
  # 내림차순 정렬 li의 각 요소를 x로 보고, -x 순서로 오름차순 정렬
  li.sort(key=lambda x: -x)
  print(li)
  
  # 3으로 나눈 나머지 오름차순 정렬 li의 각 요소를 x로 보고, x%3 순서로 오름차순 정렬
  li.sort(key=lambda x: x%3)
  print(li)
  
  
  '''결과
  [1, 2, 3, 4, 5, 6, 7, 8, 9]
  [9, 8, 7, 6, 5, 4, 3, 2, 1]
  [9, 6, 3, 7, 4, 1, 8, 5, 2]
  '''
  ```

- 람다식 응용 - 람다식을 사용한 함수프로그래밍

  ```python
  def func1(st, option=0):
      if option:
          s = st.upper()
          print(s)
      else:
          s = st.lower()
          print(s)
  
  def func2(st, option=0):
      print(option and (lambda s:s.upper())(st) or (lambda s:s.lowwer())(st))
      # option and (대문자로 바꾸기) or (소문자로 바꾸기)
  
  # 두 함수의 기능은 같다.
  ```



## 3.6. 클로저. (나는 과연 함수를 불러왔을까?)

클로저 : 함수와 함수가 처음 정의된 환경을 아우르는 말.

다른 함수를 쓸 때 클로저가 어떠한 경우에 필요한 개념인지 알 필요가 있다.

 만약 아래의 함수와 같이 정보(total)를 공유하는 코드를 작성했다고 가정. (초기 의도는 locSum과 yoursum의 total을 구분하려는 의도였다고 가정.)

```python
total=0
def locSum():
    global total
    total += 1
    print(total)

def yoursum():
    global total
    total += 3
    print(total)

locSum() # 1
locSum() # 2
yoursum() # 5
locSum() # 6
yoursum() # 9
yoursum() # 12
locSum() # 13
print(f'total = {total}')

'''결과
1
2
5
6
9
12
13
total = 13
'''
```

 위 코드의 경우 컴파일 에러가 없기 때문에 오류를 착기 굉장히 번거로움. 하나하나 중간 값을 받아보면서 오류를 찾아야하는 어려움도 있음. 이러한 문제를 해결하기 위해 존재하는 것이 클로저. (사실 함수 실행에 있어 항상 존재했지만 몰랐을 뿐.)

※ 클로저을 이해하기 위해 필요한 개념
  모듈 : 파이썬 코드로 작된 파일. 외부에서 이 모듈을 불러와서 내용에 있는 기능을 사용할 수 있음.

A.py
```python
var=12345
def a():
    print(var)
```

B.py
```python
import A

var=54321
def b():
    print(var)

A.a()
b()

'''결과
12345
54321
'''
```

결과를 보면 A.a()에서 처음 함수가 만들어진 환경의 결과값으로 가져오는 것을 알 수 있다.



아래의 코드와 결과를 보고 다른 상황에서 클로저가 어떠한 것인지 알 수 있다.

```python
var = 0

def outter():
    var = 74
    def inner():
        nonlocal var    # var = 7423 의 var을 불러옴.
        var+=1
        print(var)
    return inner
clsr1=outter()
clsr2=outter()
clsr1() # 75
clsr1() # 76
clsr1() # 77
print()
clsr2() # 75
clsr2() # 76
clsr2() # 77

'''결과
75
76
77

75
76
77
'''
```

위 결과를 통해서 알 수 있는 것은 2개 이다. 

1. 모듈에서 불러들이거나, 반환 혹은 인수로 전달되면 자신이 정의된 환경도 가져감.
   **클로저가 넘어가는 것이지 함수가 넘어가는 것이 아니다.**
2. clsr1, clsr2이 서로의 값에 영향을 주지 않는다. (독립적 동작)
   호출될 때 마다 지역 이름공간이 새로 만들어짐. **반환된 inner함수의 클로저가 다름.**



## 3.7. 장식자 (decorator) / 꾸미는 기능.

 만약 함수를 여러개 써야하는데 각각의 함수마다 같은 기능을 추가로 줘야한다면?
하나하나 입력하는 것은 굉장히 번거롭고 난잡함.
=> 이것을 위해서 필요한 기능, 데코레이터

- 데코레이터 메커니즘
  - 장식자는 기능을 추가할 함수를 인수로 받음.
  - 장식자의 내부에 추가될 기능을 함수로 정의.
  - 인수로 받은 함수를 내부에 정의된 함수에서 적절히 호출.
  - 내부 함수를 반환. (클로저에서 새로운 함수로 탄생함.)

- 데코레이터 정의 및 사용 방법 1. 함수 정의를 이용.

```python
import datetime

def de(): # 꾸며질 함수
    print("Hello Python !")

def deco(func): # 꾸미는 기능을 정의
    def new_func():
        print('today', datetime.date.today())
        func() # 인수로 받은 함수가 사용되는 자리.
    return new_func # 함수를 반환하여 사용 가능하도록 함.

deco_func1 = deco(de)
deco_func1()

'''결과
today YYYY-MM-DD
Hello Python !
'''
```



- 데코레이터 정의 및 사용 방법 2. 장식자 문법 사용.

```python
import datetime

def deco(func): # 꾸미는 기능을 정의
    def new_func():
        print('today', datetime.date.today())
        func() # 인수로 받은 함수가 사용되는 자리.
    return new_func # 함수를 반환하여 사용 가능하도록 함.

@deco
def de(): # 꾸며질 함수
    print("Hello Python !")

@deco
@deco # 2개 써도 된다.
def de2(): # 꾸며질 함수
    print("Hello Python !")

de()
de2()

'''결과
today YYYY-MM-DD
Hello Python !
today YYYY-MM-DD
today YYYY-MM-DD
Hello Python !
'''
```



## 3.8. 제너레이터(생성자) 함수, 코루틴 함수.

- 반복자 생성, 제너레이터(생성자) 함수

  ```python
  a=[1,2,3,4,5]
  it=iter(a)
  
  print(it.__next__())
  print(it.__next__())
  print(it.__next__())
  print(it.__next__())
  print(it.__next__())
  
  def my_gen():
      n=0
      while n<=10:
          yield n   # 함수 내부에서 yield라는 키워드가 사용 되면 제너레이터 함수가 됨. 함수가 대기하는 위치.
          n+=1
  # for문에서 반복가능한 객체를 전달하여 순회하는 것은 .__next__()를 이용함.
  a = my_gen()
  print(type(a))
  print(a.__next__())
  print(a.__next__())
  print(a.__next__())
  print(a.__next__())
  print(a.__next__())
  print(a.__next__())
  print(a.__next__())
  print(a.__next__())
  print(a.__next__())
  print(a.__next__())
  
  '''
  1
  2
  3
  4
  5
  <class 'generator'>
  0
  1
  2
  3
  4
  5
  6
  7
  8
  9
  10
  Traceback (most recent call last):
    File "1.py", line 29, in <module>
      print(a.__next__())
  StopIteration
  '''
  ```

- 코루틴 함수 (제너레이터의 한 종류) 알기전에 알아야할 루틴 개념.
  - 메인루틴 : 프로그램에서 주축이 되는 코드들의 묶음, 흐름.
  - 서브루틴 : 메인루틴에서 호출된 함수.
  - 메인루틴에서 서브루틴, 코루틴을 호출하면 코드 수행권한(실행)은 넘어감. 그 동안 메인루틴은 정지.
  
  - 코루틴 : 서브루틴과 달리 대기상태가 존재하는 루틴. 메인루틴처럼 하나의 흐름을 가진다고 보면된다.
  
- 코루틴 함수 사용1.
  ```python
  >>> def co_routine():
  ...     total=0
  ...     while True:
  ...         n=(yield) # (yield) 표현식, send를 통해서 값을 전달 받음, 전달받기 전까지 대기.
  ...         total+=n
  ...         print(f'total = {total}')
  ...
  >>> a= co_routine()
  >>> a.__next__() # 코루틴 함수는 next를 한번만 호출함. (yield)문 전까지만 실행되기 때문.
  >>> a.send(1) # 코루틴 함수의 yield에 값을 넘겨줌. 코루틴의 특징.
  total = 1
  >>> a.send(1)
  total = 2
  >>> a.send(3)
  total = 5
  >>> a.send(9)
  total = 14
  >>> type(a)
  <class 'generator'> # 코루틴이 제너레이터임을 보여줌.
  ```
  
- 코루틴 함수 사용2.
  ```python
  >>> def co_ro():
  ...     total=0
  ...     while True:
  ...         n=(yield total) # 반환값을 total로 지정해줌. send 혹은 __next__에서 반환.
  ...         total+=n
  ...
  >>> a=co_ro()
  >>> a.__next__()
  0
  >>> a.send(5)
  5
  >>> a.send(7)
  12
  >>> a.send(9)
  21
  >>>
  ```

- 코루틴을 사용 예시

  ```python
  from time import sleep
  
  def corouA():
      n=0
      while True:
          n=(yield n)
          sleep(0.1) # 0.1초 해당 루틴 일시정지.
          if n%10==3 or n%10==6 or n%10==9 :
              print("A : 박수")
          else :
              print(f'A : {n}')
          n+=1
  
  n=0
  a=corouA()
  a.__next__()
  
  while True:
      n=a.send(n)
      sleep(0.1)
      if n%10==3 or n%10==6 or n%10==9 :
          print("B : 박수")
      else :
          print(f'B : {n}')
      n+=1
  '''결과
  A : 0
  B : 1
  A : 2
  B : 박수
  A : 4
  B : 5
  A : 박수
  B : 7
  A : 8
  B : 박수
  A : 10
  B : 11
  A : 24
  B : 25
  A : 박수
  B : 27
  A : 28
  B : 박수
  A : 30
  ...
  '''
  ```

  

# 4. Python 모듈과 패키지
 모듈과 패키지는 외부의 파일 외부의 코드를 사용하기 위한 개념. 모든 코드를 하나의 파일에 작성하기 어렵고, 일부 재사용 가능한 코드를 따로 관리하기 위해 사용.
모듈 : 파이썬 파일
패키지 : 관련 모듈을 모아서 사용하는 폴더



## 4.1. 모듈

- import 처음

  ```python
  # test_module0.py
  print("Hellow Python.")
  ```
  
  ```python
  # test_module_user0.py
    import test_module
  
  '''결과
  Hellow Python!!!
  '''
  ```
  
  - import
  
    > 외부코드를 불러와서 실행 시킬 수 있도록 해줌.

- import로 모듈 내부의 기능 불러오기

  ```python
  # test_module.py
  
  def print_hellow_python():
      print("Hellow Python.")
  
  print(__name__)
  ```

  
  ```python
  # test_module_user1.py
  import test_module
  
  test_module.print_hellow_python()
  
  '''결과
  test_module
  Hellow Python.
  '''
  ```
  ```python
  # test_module_user2.py
  from test_module import print_hellow_python
  
  print_hellow_python()
  
  '''결과
  test_module
  Hellow Python.
  '''
  ```
  ```python
  # test_module_user3.py
  from test_module import print_hellow_python as php
  
  php()
  
  '''결과
  test_module
  Hellow Python.
  '''
  ```
  ```python
  # test_module_user4.py
  import test_module, test_module0
  
  test_module.print_hellow_python()
  print(__name__)
  '''결과
  test_module
  Hellow Python!!!
  Hellow Python.
  __main__
  '''
  ```

  - import
  
    > 사용할 패키지, 모듈, 클래스, 함수를 지정.
    > 콤마(,)를 이용해서 여러개를 한번에 지정할 수 있다.
    > 만약 *를 사용하면 모든 식별자를 불러온다.
  
  - from
  
    > 사용할 모듈, 클래스, 함수가 들어있는 클래스 혹은 모듈을 지정.
  
  - as
  
    > 사용할 기능의 이름이 긴 경우, 이름 중복이 있는 경우에 이름을 새로 정의해주는 기능.
  
  - \_\_name\_\_
  
    > 파이썬에서 자동으로 만들어지는 변수.
    > 직접 실행시키는 경우 "\_\_main\_\_"
    > 모듈로써 실행시키는 경우 "모듈명" 으로 지정 됨.

- 모듈 검색

  ```python
  import sys
  print(sys.path)
  ```

- 명령행 인수 전달

  ```python
  import sys
  sys.argv # 콘솔에서 파이썬 명령어를 통해서 실행할 경우 모듈이름이 리스트의 0번째 인자로 들어감. 나머지는 띄어쓰기를 기준으로 진자를 구분해서 입력됨.
  ```

- \_\_pycache_\_

  ```python
  import py
  ```



## 4.2. 패키지

- test_package 패키지 만들기

  | .\test_package |
  | -------------- |
  | \_\_init\_\_.py<br />first_module.py<br />second_module.py |

  



























# 6. Python Class

 클래스는 임의의 어떠한 결과를 저장하기 위한 객체로 생각하면 된다. 예를  들어서 자동차의 경우 각 부품의 제조번호를 기록하는 경우를 생각하면 된다. 하나의 객체(자동차)에 수많은 정보(모델명, 색상, 엔진, 모터, 스프링, 제조일자 등등)이 있을 것이고, 각 "자동차마다" 따로 정보를 관리하기 위해서 사용한다고 생각하면 편하다.
 문제해결을 위해 필요한 하나의 분류가 되는 개념(예를 들어 자동차라는 개념)을 클래스로 정의한다.  이 클래스를 이용해서 하나의 객체(예로 내가 빌린 자동차, 객체대신 자동차의 인스턴스라고도 함.)로써 정의 하여 필요한 정보(차의 색상=흰색, 차종=아반떼)를 정의하여 관리 혹은 사용하겠다는 것이다. 중요한 것은 클래스를 사용함으로써 객체지향 프로그래밍을 하고, 이 장점을 쓴다는 것이다.

- Class 정의 방법

  ```python
  class ex_Car(object) : # class에서 object를 상속 받음. 상속받지 않으려면 비우면됨.
      def __init__(self, year, color, model, price): # 생성자에서 받아올 인자를 결정, 인스턴스를 초기화.
          self.year = year
          self.color = color
          self.model = model
          self.price = price
      # 추가로 클래스에서 사용할 메서드를 정의할 수 있다.
  ```

  





# 7. Python 예외 처리

ValueError
SyntaxError









# 7. Python 데코레이터





















# 파이썬 관련 참고 자료

- Python 공식 문서 : https://docs.python.org/3/

- VS Code 문서 : https://demun.github.io/vscode-tutorial/



## VS Code Extention 정리.

- Beautify : 
- Django : 
- JavaScript : 
- open in browser : `Shift` + `Alt` + `B` 로 해당 파일을 Browser로 실행.
- Python : .py 파일 수정시 디버깅.
- SQLite : DB켜서 볼 수 있음.
- vscode-icons : 기본 아이콘 설정은 색이 흐리고 어두워서 구분이 어려움. 밝고 선명한 아이콘으로 바꿈.