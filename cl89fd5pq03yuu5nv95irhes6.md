# [JavaScript] 자연수 뒤집어 배열로 만들기

# 문제 설명
자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

# 제한 조건
n은 10,000,000,000이하인 자연수입니다.
# 입출력 예
<table>
<tr><th>n</th><th>return</th></tr>
<tr><td>12345</td><td>[5,4,3,2,1]</td></tr>
</table>

# 나의 풀이
```javascript
function solution(n) {
return n.toString().split('').reverse().map(Number)
}
```

> 점점 재미있어지는 프로그래머스! 오늘의 문제도 굉장히 흥미로웠다. 일단 숫자를 스트링처리를 하기 위해 toString()사용. 그리고 숫자를 배열에 넣어주기위해 split()사용. 그다음 reverse()를 사용해 배열이 거꾸로 들어가게 만든다. 그 후, map으로 돌려 각 element를 Number로 변환 ! 글을 쓰다보니.. map은 배열로 반환한다는 사실을 이용해서 배열을 한번만 사용하는 방법은 없을까..? 라는 생각이 든다. 시도해보자! 

# 시도한 방법
```
function solution(n) {
    return [...n.toString()].map(Number).reverse()
}
```
> string이 배열과 비슷한 성질을 이용해 뭔가를 해볼려고 했지만 떠오르지 않았다. 대신 spread 연산자를 이용하여 문제를 풀어봤는데 효율적으로 풀린건지는 잘 모르겠다. 함수를 하나 적게 사용했으니 좋은건가!?