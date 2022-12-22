# [JavaScript] 짝수와 홀수

## 문제 설명
- 정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요.

## 제한 조건
- num은 int 범위의 정수입니다.
- 0은 짝수입니다.

## 입출력 예
<table>
<tr><th>num</th><th> return</th></tr>
<tr><td> 3</td><td>"Odd"</td></tr>
<tr><td> 4</td><td>"Even"</td></tr>
</table>

> 프로그래머스 문제를 보자마자 풀어버리는 날이 오다니 🥲 문제가 아주 아주 쉽긴 했지만 ㅋㅋㅋ 몇주전 배웠던 삼항연산자를 이용해서 풀었다.

## 나의 답
```
function solution(num) {
return num%2 === 0 ? "Even" : "Odd"
}
```

## 다른사람의 답을 보고 배운 점

```
function evenOrOdd(num) {
  return num % 2 ? "Odd" : "Even";
}
```
> 이 분도 삼항연산자를 이용했지만 0이 false인 속성을 이용하여 문제를 푼게 인상깊었다 👍