# [JavaScript] includes() & replace()

# 문제

- s는 여러 괄호들로 이루어진 String 인자입니다. s가 유효한 표현인지 아닌지 true/false로 반환해주세요. 종류는 '(', ')', '[', ']', '{', '}' 으로 총 6개 있습니다. 아래의 경우 유효합니다. 한 번 괄호를 시작했으면, 같은 괄호로 끝내야 하고 괄호 순서가 맞아야합니다.

예를 들어 아래와 같습니다.

```
s = "()"
return true

s = "()[]{}"
return true

s = "(]"
return false

s = "([)]"
return false

s = "{[]}"
return true
```

> 처음엔 이게 무슨말인지 잘 몰랐는데 하나씩 천천히 생각해 보고 이해했다. 처음에 들었던 생각은 '아.. 컴퓨터가 어떻게 알고 '('와 ')'가 짝꿍인지 어떻게 알지... ' 였다. 다시 정신을 차리고 접근 방식을 생각해 보았다. 당연히 반복문을 사용해야하고 또 그다음에... if문을 써서 하나씩 하나씩 다 물어봐야하나? 라고 생각하던 순간, 

> "replace" 와 "includes"를 쓰면 되요! 라고 뒤에서 들리는 hint 😂

문제를 풀기 전, `replace` 와 `includes`의 syntax를 알아보자.

```
//replace syntax

const p = "I love you"

console.log(p.replace('love', 'hate')); // expected output : "I hate you"

//includes syntax

const arr = [1, 2, 3];

console.log(arr.includes(2));
// expected output: true

```

> replace는 선택한 요소를 다른 요소와 대체시켜주고 include는 지정된 값안에 해당 값이 있으면 boolean으로 return해준다. 이제 재료는 준비되었으니 요리를 해보자. 일단 while을 사용하여 반복문을 사용하여 각각의 요소를 확인할수있도록 해주자

```
while(s.includes('()') || s.includes('[]') || s.includes('{}') //  s 배열 안에 indicate한 요소가 있으면 계속 반복해준다.
{ s = s.replace("(),"")
  s = s.replace("[],"")
  s = s.replace("{},"")
} // 반복하는 중에 () or [] or {} 가 있으면 빈값으로 대체해준다.

return s === ""? true : false; // s가 빈값이면 true, 그게 아니라면 false를 return 한다.
```

> 어떻게 생각하면 이런 식을 도출할 수 있는걸까? 이걸 발견한 사람은 천재가 분명하다. 앞으로 더 다양한 관점으로 문제에 접근해봐야겠다.