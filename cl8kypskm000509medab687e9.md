# [JavaScript] 서울에서 김서방 찾기 (indexOf)

# 문제 설명
String형 배열 seoul의 element중 "Kim"의 위치 x를 찾아, "김서방은 x에 있다"는 String을 반환하는 함수, solution을 완성하세요. seoul에 "Kim"은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.

## 제한 사항
seoul은 길이 1 이상, 1000 이하인 배열입니다.
seoul의 원소는 길이 1 이상, 20 이하인 문자열입니다.
"Kim"은 반드시 seoul 안에 포함되어 있습니다.
## 입출력 예
<table>
<tr><th>seoul</th><th>return</th></tr>
<tr><td>["Jane", "Kim"]</td><td>"김서방은 1에 있다"</td></tr>
</table>
	
# 나의 풀이
```
const solution = seoul => `김서방은 ${seoul.indexOf('Kim')}에 있다`
```

> 인덱스를 찾는 함수가 분명히 있을꺼라고 생각하고 구글링을 해보니 indexOf였다. 바로 적용! 금방 풀었다 🤓
김서방이 배열안에 없는 경우도 문제에 포함되면 좀 더 어려울거라고 생각한다.