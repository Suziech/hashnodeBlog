# [JavaScript] Algorithm practice

# 문제
- reverse 함수에 정수인 숫자를 인자로 받습니다.
- 그 숫자를 뒤집어서 return해주세요.
- x: 숫자 return: 뒤집어진 숫자를 반환!
- 예들 들어, x: 1234 return: 4321 
- x: -1234 return: -4321
- x: 1230 return: 321

> 아.. 이미 함수에 reverse라고 쓰여있었네 ㅋㅋㅋ 이 문제는 int 를 string으로 변환시키고 arr에 넣어 배열 순서를 뒤집어 주어 풀 수 있다.

```
const reverse = x => {

}
```

> 일단 정수인 숫자 String()을 사용해서 string으로 변환 시켜준다.

```
const reverse = x => {
  String(x);
}
```

> 그리고 split()을 사용하여 array에 넣어준다.

```
const reverse = x => {
  String(x).spilt("");
}
```

> 배열에 넣어줬으니 이제 reverse()를 사용해서 순서를 뒤집어준다.

```
const reverse = x => {
  String(x).spilt("").reverse();

//expected : ["4", "3", "2", "1", "-"]
}
```
> 이제 "-"인지 알아내고  "-"가 있으면 제거한 후, 배열을 하나로 합치고 int로 변환 한 후, "-1" 을 곱해주거나 아니면 그대로 return 하면 된다!

 ```
const reverse = x => {
  let arr = (String(x).split('').reverse()); // ["4", "3", "2", "1", "-"]
  let filteredArr = arr.filter((minus) => minus !== '-');
  let result = Number(filteredArr.join(''));
  if(arr[arr.length-1] === '-'){
    return -result;
      } else {
      return result;
      }

```

> 새롭게 알게된 함수를 배울 수 있고 사용할 수 있어서 좋았다!  