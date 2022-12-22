# [JavaScript] 정수 내림차순으로 배치하기 (descending sort)

# 문제 설명
함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다.
## 제한 조건
n은 1이상 8000000000 이하인 자연수입니다.
## 입출력 예
<table>
<tr><th>n</th><th>return</th></tr>
<tr><td>118372</td><td>873211</td></tr>
</table>

> 처음에 문제를 착각해서 숫자를 그냥 flip했다. 근데 자세히 읽어보니 큰수부터 정렬하는거였.. 일단 string으로 변환 후 배열에 넣어주고 sort()로 정렬시켜주니 작은수부터 큰수로 정렬이 됬다. reverse()를 사용해서 배열의 순서를 뒤집어주고 join()으로 split으로 나눠준걸 다시 합쳐준다. 그리고 전체를 Number()로 감싸주어 int로 전환!

# 나의 풀이
```
function solution(n) {
return Number(n.toString().split('').sort().reverse().join(''))
}
```