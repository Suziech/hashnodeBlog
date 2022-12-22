# [JavaScript] 문자열 내림차순으로 배치하기 (Place strings in descending order)

# 문제 설명
- 문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.
- s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.

# 제한 사항
- str은 길이 1 이상인 문자열입니다.
# 입출력 예
<table>
<tr><th>s</th><th>return</th></tr>
<tr><td>"Zbcdefg"</td><td>"gfedcbZ"</td></tr>
</table>

# 나의 풀이
```
const solution = s => s.split('').sort().reverse().join('');
```

> 소문자 대문자도 크고 작음이 있다는 사실을 몰라서 풀때 좀 헤매었다. 'a'와 'A'로 비교해보니 소문자가 크다는 식이 true로 반환됬다. 그러므로 sort()함수를 적용하면 작은 'A'가 앞으로 그리고 'a'가 뒤로 배치된다. 대문자를 뒤로 보내야하는 조건을 봤을때 reverse전에는 대문자가 앞으로 가야한다. 이 원리를 알고나서는 쉽게 풀 수 있었다.