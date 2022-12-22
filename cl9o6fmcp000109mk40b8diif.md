# [JavaScript] null vs undefined in JavaScript

# `null` vs `undefined` = 없음


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666699803820/tqguZkGOI.png align="left")

> 사실 이 사진이 거의 모든 것을 설명한다고 볼 수 있다.

## undefined : 
- 명시적으로 지정 가능
- 값이 존재하지 않을 때 자바스크립트 엔진이 자동부여 (자바스크립트 엔진은 어떤 값이 지정될 것이라고 예상됬지만 지정되지 않은 경우 undefined를 return 함) : 호이스팅
- 변수에 값이 존재하지 않음

- 아래와 같은 상황이 이에 해당
    1. 값을 대입하지 않은 변수, 즉 데이터 영역의 메모리주소를 지정하지 않은 식별자에 접근 할 때
    2. 객체 내부에 존재하지 않는 프로퍼티에 접근하려고 할 때
    3. return 문이 없거나 호출되지 않는 함수의 실행 결과


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666691247708/7ZQlJ-Deb.png align="left")
> 설명 3 과 같이 function에서 return 이 없는 경우 그림과 같이 undefined가 출력된다.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666691546287/DEuChodV0.png align="left")
> undefined가 return 되는 상황

## null : 
- `비어있음`을 명시적으로 나타내고 싶을 때 사용
- typeof null = object => 자바스크립트 자체 오류
- `없음` 을 표현

결론 : 각각의 본래 의미에 따라 `없음`을 표현하기 위해서는 undefined 대신 null을 사용해야함. 

> data type이 다름
>> undefined : undefined

>> null : object

> 연산결과가 다름
>> undefined + 1 

>>// return NaN

>> null + 1

>> // return 1

[도움이 된 웹사이트](https://flexiple.com/javascript/undefined-vs-null-javascript/)