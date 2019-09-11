[TOC]

# 0. Python 준비.

파이썬의 특징

- 스크립트 언어
- 동적 타이핑 언어 : 선언과 변수를 정의하는 과정에서 타입을 신경쓸 필요가 없다는 장점.

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



### 2.2. if 문

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



## 2.3. 반복문 for

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



### 2.3.1. range 함수

python 의 range함수는 range라는 객체를 생성하는 함수이다. range 또한 iterable한 객체로 for문에서 원하는 횟수 만큼 반복 할 때 많이 사용한다.

| range 함수         | 사용 결과                                                    |
| ------------------ | ------------------------------------------------------------ |
| range(num)         | 0부터 num-1 까지의 숫자를 가진 range 객체                    |
| range(n1, n2)      | n1부터 n2 - 1 까지의 숫자를 가진 range 객체                  |
| rnage(n1, n2, gab) | n1부터 gab 씩 더해진 숫자  중 n2 보다는 작은 수를 가진 range 객체 |



### 2.3.2. break 문

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



### 2.3.3. continue 문

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



### 2.3.4. for else 문

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



### 2.3.5. 리트스 내포 확장 [expr for x in iterable객체 if 조건식]

```python
>>> [x for x in range(1,10) if x%2==0]
[2, 4, 6, 8]
>>> [x**3 for x in range(1,10) if x%2==0]
[8, 64, 216, 512]
>>> ['짝' if x%2==0 else '홀']
```



## 2.4. while 문

```python
while 조건문:
    실행문
# 조건문이 True일 때 실행문이 실행된다. 설정하기에 따라 무한으로 반복 가능.
```

























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