# [JavaScript] 자릿수 더하기

# 문제 설명
- 자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.
- 예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

# 제한사항
- N의 범위 : 100,000,000 이하의 자연수

# 입출력 예
<table>
<tr><th>N</th><th> answer</th></tr>
<tr><td>123</td><td>6</td></tr>
<tr><td> 987</td><td>24</td></tr>
</table>

## 입출력 예 설명
- 입출력 예 #1

  - 문제의 예시와 같습니다.

- 입출력 예 #2

  - 9 + 8 + 7 = 24이므로 24를 return 하면 됩니다.

> 일단, 숫자 하나하나를 분리해야한다고 생각해서 n을 toString()을 이용해서 string으로 변경후 split()을 사용하여 배열안에 하나 하나 넣어주었다. 그런 다음 더하기를 해야하니 각각의 스트링화된 숫자를 숫자화 시켜야 해서 map을 이용하여 각각의 요소를 number로 변환했다. 그 후, reduce()를 이용하여 각각의 배열의 숫자를 더해주었다

### 나의 답
```
function solution(n)
{return result = n.toString().split('').map(Number).reduce((prev,curr)=>prev+curr);}
```

> **새로 알게 된 사실**
>> map(Number) : map이 배열의 각각의 요소를 돌며 숫자로 변환시켜준다. 

>> 반대로 map(String)을 실행시켜주면 숫자인 요소들을 스트링으로 변환시켜준다.

```jsx
[0, 1, 2].map(String) // expected : ['0', '1', '2']
//[0, 1, 2].map(item => String(item))
['0', '1', '2'].map(Number) // expected: [0, 1, 2]
//['0', '1', '2'].map(item => Number(item)) 
```

>> reduce()
>> 이전값을 누적하여 계산을 진행해 준다.