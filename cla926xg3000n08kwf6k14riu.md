# [JavaScript] RegExp

# 정규 표현식*(Regular Expression)*이란?
- 일정한 패턴을 가진 문자열의 집합을 표현하기 위해 사용하는 형식 언어(formal language)
- 문자열을 대상으로 **패턴 매칭 기능** 제공 (패턴 매칭 기능이란 특정 패턴과 일치하는 문자열을 검색하거나 추출 또는 치환할 수 있는 기능)

```
//사용자로부터 입력받은 휴대폰 번호
const tel = '010-1234-563팔';
//정규표현식 리터럴로 휴대폰 전화번호 패턴 정의
const regExp = /^\d{3}-\d{4}-\d{4}$/;
//tel이 휴대폰 번호 패턴에 매칭하는지 test
regExp.test(tel); // false
```

- 위와 같이 정규표현식을 사용하면 반복문과 조건문 없이 패턴을 정의하고 테스트하는 것으로 간단히 체크 할 수 있다. 다만 정규표현식은 주석이나 공백을 허용하지 않고 여러가지 기호를 혼합하여 사용하기 때문에 가독성이 좋지 않다.

# 정규 표현식의 생성

- 정규표현식 리터럴 & RegExp 생성자 함수 사용 가능

✨ 정규표현식 리터럴 예시

```
const target = 'Is this all there is?'
//패턴 : is
//플래그 : i => 대소문자를 구별하지 않고 검색
const regexp = /is/i;

regexp.test(target) //true
```

✨ RegExp 생성자함수 예시

```
const target = 'Is this all there is?';
const regexp = new RegExp(/is/i);

regexp.test(target); //true
```

RegExp 생성자 함수를 사용하면 변수를 사용해 동적으로 RegExp 객체를 생성할 수 있다.
```
const count=(str,char) => (str.match(new RegExp(char, 'gi')) ?? []).length;

count('Is this all there is?', 'is'); // 3
count('Is this all there is?', 'xx'); // 0
```

# 플래그
<table>
<tr><th>플래그</th><th>의미</th><th>설명</th></tr>
<tr><td>i</td><td>Ignore case</td><td>대소문자를 구별하지 않고 패턴을 검색</td></tr>
<tr><td>g</td><td>Global</td><td>대상 문자열 내에서 패턴과 일치하는 모든 문자열 전역 검색</td></tr>
<tr><td>m</td><td>Multi line</td><td>문자열의 행이 바뀌더라도 패턴검색</td></tr>
</table>

- 플래그는 option이므로 선택적으로 사용가능
- 순서와 상관없이 하나 이상의 플래그를 동시에 설정가능
- 어떠한 플래그를 사용하지 않은 경우 대소문자 구별하여 패턴 검색하고 문자열에 패턴 검색 매칭 대상이 1개 이상 존재해도 첫 번째 매칭한 대상만 검색하고 종료

프로그래머스에서 필요한 `replace.prototype.replace`에 대해 알아보자!

# String.prototype.replace

replace method는 대상 string에서 첫 번째 인수로 전달받은 문자열 또는 정규표현식을 검색하여 두 번째 인수로 전달한 문자열로 치환한 문자열을 반환한다.

```
const str = "Hello world";
//str에서 첫 번째 인수 'world'를 검색하여 두 번째 인수 'Lee'로 치환한다.
str.replace('world', 'Lee') // 'Hello Lee'
```

replace method의 첫 번째 인수로 정규표현식을 전달 할 수도 있다.

```
const str = "Hello world";
//'hello'를 대소문자를 구별하지 않고 전역 검색한다.
str.replace(/hello/gi, 'Lee') // 'Lee world'
```

✨ 특수 문자를 제거할 때는 String.prototype.replace method를 사용한다.
```
const target = 'abc#123'
//특수 문자를 제거한다.
target.replace(/[^A-Za-z0-9]/gi, ' '); // -> abc123
```

# 프로그래머스 문제풀이 (모음 제거)

### 문제 설명
- 영어에선 `a, e, i, o, u` 다섯 가지 알파벳을 모음으로 분류합니다. 문자열 my_string이 매개변수로 주어질 때 모음을 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

### 제한사항
`my_string`은 소문자와 공백으로 이루어져 있습니다.
`1 ≤ my_string의 길이 ≤ 1,000`

### 입출력 예

<table>
<tr><th>my_string</th><th>result</th></tr>
<tr><td>"bus"</td><td>"bs"</td></tr>
<tr><td>"nice to meet you"</td><td>"nc t mt y"</td></tr>
</table>
	
### 입출력 예 설명

**입출력 예 #1**

- "bus"에서 모음 u를 제거한 "bs"를 return합니다.

입출력 예 #1

- "nice to meet you"에서 모음 i, o, e, u를 모두 제거한 "nc t mt y"를 return합니다.

### 나의 풀이

```
const solution = my_string => my_string.replace(/[aeiou]/g,'')
```

> 이 문제 푸는데 또 많은 시간들이 걸렸다. 하지만 정규식을 알아야 간단히 풀 수 있을것이라고 생각해서 정규식을 살짝 공부 해봤다. 내용이 많아서 일단 필요한 부분을 중점적으로 공부하여 문제를 풀자고 생각했다. 일단 문자열 검색 패턴으로는 quotes를 생략하고 `/`로 감싼 후 `[]`에 찾고자하는 문자열들을 넣은 후 플래그 g를 추가하여 전역에서 검색하여 replace to `''` 해주는 방식으로 풀었다. 정규식이 복잡하게 생겨서 좀 기피했었는데 이렇게 쉽게 문제를 풀 수 있는 존재였다니 !! ✨ 