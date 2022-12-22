# [JavaScript] 짝수의 합 (Sum of even numbers)

# 문제 설명
정수 n이 주어질 때, n이하의 짝수를 모두 더한 값을 return 하도록 solution 함수를 작성해주세요.

# 제한사항
0 < n ≤ 1000

# 입출력 예
<table>
<tr><th>n</th><th>result</th></tr>
<tr><td>10</td><td>30</td></tr>
<tr><td>4</td><td>6</td></tr>
</table>

# 입출력 예 설명

**입출력 예 #1**

n이 10이므로 2 + 4 + 6 + 8 + 10 = 30을 return 합니다.

**입출력 예 #2**

n이 4이므로 2 + 4 = 6을 return 합니다.

> 문제를 평소처럼 풀었다. 배열에 짝수를 넣은 후, reduce로 배열의 모든 값을 더한 수를 구하려고 했지만 런타임 에러로 제출 실패했다. reduce를 사용하지 않고 풀어야 통과될것 같았다. 하지만 잘 생각이 나지 않는다. 어떻게 접근해야하지?

![Screenshot 2022-10-04 at 9.01.12 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664843524665/mLDWAatm2.png align="left")

> 사실 `+=`을 이용해서 배열에 넣지 않고 쉽게 해결 가능한 문제였다. for문을 돌려서 n+1보다 작은 수들을 구해서 그 각각의 수가 %2했을 때 나머지가 0이면 result에 더해주는 방식이다. 이렇게 제출하니 통과되었다!

# 나의 풀이

```
const solution = n => {
    result = 0;
    for(let i=1; i<n+1; i++){
    i%2 === 0 ? result+=i : null
    }
    return result;
}
```

# 신박했던 다른 사람의 풀이

```
function solution(n) {
    var answer = 0;

    for(let i=2 ; i<=n ; i+=2)
        answer += i;

    return answer;
}
```
> 아예 초기값을 2로 잡고 2씩 증가시켜주는 방법이 있었다니!! 왜 여기까지 생각을 못한것인가 😣

```
function solution(n) {
    var half = Math.floor(n/2);
    return half*(half+1);
}
```

> 와.. 이건 수학적 머리가 있어야 가능한건가...?!