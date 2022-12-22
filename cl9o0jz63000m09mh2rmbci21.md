# [JavaScript] Data Types

# 01 데이터 타입
## 01 데이터 타입의 종류

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666683366977/RgiZeiMVY.png align="left")

<details>
<summary>
Primitive type 에서 Symbol이란?
</summary>
Symbols are completely unique identifiers. 
일반적으로 심볼 타입은 객체의 프로퍼티 키를 고유하게 설정함으로써 프로퍼티 키의 충돌을 방지하기 위해 사용
</details>

<details>
<summary>
Reference type에서 RegExp이란?
</summary>
= Regular Expression : 정규 표현식
The RegExp object is used for matching text with a pattern.
정규표현식은 "특정 패턴의 문자열"을 찾기 위한 표현 방식
</details>

<details>
<summary>
Reference type에서 WeakMap이란?
</summary>
The primary difference between Map and WeakMap is that the WeakMap key can’t be primitive values.
</details>

<details>
<summary>
Reference type에서 WeakSet이란?
</summary>
WeakSet is considered equivalent to Set. Yet, only objects and not primitives may be added to WeakSet.
</details>

## 02 데이터 타입에 관한 배경지식
- 8 bits = 1 byte
- 모든 data는 byte단위의 식별자 (identifier), 더 정확하게 메모리 주솟값(Memory address)을 통해 서로 구분/연결 가능
- 식별자 (identifier) : 변수 이름
- 변수 (variable) : 변할 수 있는 데이터 (숫자, 문자, 객체, 배열 등등)
## 03 변수 선언과 데이터 할당
- 변수 선언에 대한 메모리 영역 변화
```
let a;
a = 'abc'
a = 'abcde'
```
<table>
<tr><th>주소</th><td>1002</td><td>1003</td><td>1004</td></tr>
<tr><th>데이터</th><td></td><td>이름 : a / 값 : `5005`</td><td></td></tr>
<tr><th>주소</th><td>5003</td><td>5004</td><td>5005</td></tr>
<tr><th>데이터</th><td></td><td>'abc'</td><td>'abcde'</td></tr>
</table>
- 사용자가 a에 접근하고자 하면 컴퓨터는 메모리에서 a라는 이름을 가진 주소를 검색해 해당 공간에 담긴 데이터 반환함
- 변수의 데이터를 변경하면 같은 주소가 아닌 다른 주소에 새로 입력함 : 변수 데이터 영역이 분리되어 중복된 데이터에 대한 처리 효율이 높아짐 (사용해야할 바이트가 고정되있지 않아 불필요한 공간이 생기지 않음)
## 04 기본형 데이터와 참조형 데이터
- 불변값 : boolean, null, undefined, Symbol
- 불변값의 성질 : 한번 만든 데이터 값을 변경할 수 없고 변경은 새로 만드는 동작을 통해서만 이루어짐. 한번 만들어진 값은 garbage collecting을 당하지 않는 한 영원히 변하지 않음
-가변값 : 기본형 데이터와의 차이는 객체의 변수(property)영역이 별도로 존재함
```
let obj1 = {
        a:1,
        b: 'bbb'
      };
```
<table>
<tr><th>주소</th><td>1002</td><td>1003</td><td>1004</td></tr>
<tr><th>데이터</th><td></td><td>이름 : obj1 / 값 : `5003`</td><td></td></tr>
<tr><th>주소</th><td>5003</td><td>5004</td><td>5005</td></tr>
<tr><th>데이터</th><td>`7103`</td><td>1</td><td>'bbb'</td></tr>
</table>
<table>
<tr><th>주소</th><td>7103</td><td>7104</td><td>7105</td></tr>
<tr><th>데이터</th><td>이름 : a / 값 : 5004</td><td>이름 : b / 값 : 5005</td><td></td></tr>
</table>
## 05 불변 객체

## 06 undefined와 null
## 07 정리