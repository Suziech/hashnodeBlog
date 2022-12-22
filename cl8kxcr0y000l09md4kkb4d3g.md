# [JavaScript] 두 정수 사이의 합 (the sum between 2 integers)

# 문제 설명
두 정수 a, b가 주어졌을 때 a와 b 사이에 속한 모든 정수의 합을 리턴하는 함수, solution을 완성하세요.
예를 들어 a = 3, b = 5인 경우, 3 + 4 + 5 = 12이므로 12를 리턴합니다.

## 제한 조건
a와 b가 같은 경우는 둘 중 아무 수나 리턴하세요.
a와 b는 -10,000,000 이상 10,000,000 이하인 정수입니다.
a와 b의 대소관계는 정해져있지 않습니다.

## 입출력 예
<table>
<tr><th>a</th><th>b</th><th>return</th></tr>
<tr><td>3</td><td>5</td><td>12</td></tr>
<tr><td>3</td><td>3</td><td>3</td></tr>
<tr><td>5</td><td>3</td><td>12</td></tr>
</table>

> 요새 문제가 급 어려워졌네.. 🫠 
> a까지의 배열, b까지의 배열을 구해서 중복된 값 제거하고 남은수를 다 더하고 마지막에 a/b중 큰숫자를 더해주자! 라고 생각했는데 중간에 막혀버렸고 산으로가는 느낌으로 취소.. 다른방법을 찾아야한다. 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664235479887/YqXcCny2G.png align="left")

> 그 다음으로 시도한 방법. a에서 b를 빼주고 절대값으로 만들어준다 (Math.abs()) 그다음 a와 b에서 큰 수를 찾은 후, 절대값 만큼 빼준 후 더해준다...? 아.. 머리가 안돌아가네? 구글링해보니 가우스 공식 뭐.. 이런게 나오는데 공식을 외워야 하는건가..😭 다른 방법은 없는것인가...? 사람들에게 물어보고 다녀야겠다.

## 나의 풀이
```
function solution(a, b) {
    if (a === b) {
        return a
    }
    
    let addNum = 0;
    if (a < b) {
        for(let i=a; i<b+1; i++){
            addNum += i;
        }
        return addNum;
    } else {
        for(let i=b; i<a+1; i++){
            addNum += i;
        }
        return addNum;
    }
}
```

> 문제를 풀었다! ㅋㅋㅋ 여기저기 물어보고 다녀서 얻어낸 결론. 사실 지금 보면 천천히 생각하고 진행했으면 충분히 가능한 부분이였는데 왜이렇게 겁먹었던거지 싶다. 특별한 함수가 들어가는것도 아니고 코딩문제풀이에 자주 사용하는 if 와 for을 사용하는거 밖에 없는데.. 😫 앞으로 천천히 computing적 사고를 하며 더 천천히 생각해봐야겠다.