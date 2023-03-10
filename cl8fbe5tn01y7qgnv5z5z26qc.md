# [JavaScript] 문자열을 정수로 바꾸기 (string to integer)

# 문제 설명
문자열 s를 숫자로 변환한 결과를 반환하는 함수, solution을 완성하세요.

## 제한 조건
s의 길이는 1 이상 5이하입니다.
s의 맨앞에는 부호(+, -)가 올 수 있습니다.
s는 부호와 숫자로만 이루어져있습니다.
s는 "0"으로 시작하지 않습니다.
## 입출력 예
예를들어 str이 "1234"이면 1234를 반환하고, "-1234"이면 -1234를 반환하면 됩니다.
str은 부호(+,-)와 숫자로만 구성되어 있고, 잘못된 값이 입력되는 경우는 없습니다.

> 문제가 길어서 어려운 문제인 줄 알았는데 간단히 말해서 string으로 표현된 숫자를 integer형식으로 변경하는 것! 설마 했는데 Number(string)으로 맞췄다! 이걸 블로그에 써야하나 고민했는데 다른사람들의 풀이를 보고 써야겠다고 생각했다.

# 나의 풀이
```
function solution(s) {
return Number(s)
}
```

# 다른 사람의 풀이
```
function strToInt(str){
  return str/1
  }
```

```
function strToInt(str){
  return  +str;
}
```

> 위의 두 풀이는 인상깊었던 코드들이다. 함수를 사용하지않고 풀어냈다. 직접 확인 해 보니 str/1, str-0, str*1 들이 working 했지만 +str은 작동하지 않았다. 함수를 사용하지않고 string을 number로 변경시키는 방법들! 신기하다. 🤓