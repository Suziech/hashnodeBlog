# [JavaScript] 최댓값 만들기 (1) (create maximum number(1))

# 문제 설명
정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 return하도록 solution 함수를 완성해주세요.

# 제한사항
0 ≤ numbers의 원소 ≤ 10,000
2 ≤ numbers의 길이 ≤ 100
# 입출력 예
<table>
<tr><th>numbers</th><th>result</th></tr>
<tr><td>[1, 2, 3, 4, 5]</td><td>20</td></tr>
<tr><td>[0, 31, 24, 10, 1, 9]</td><td>744</td></tr>
</table>
	
	
# 입출력 예 설명
**입출력 예 #1**

  - 두 수의 곱중 최댓값은 4 * 5 = 20 입니다.

**입출력 예 #1**

  - 두 수의 곱중 최댓값은 31 * 24 = 744 입니다.

# 내가 처음에 접근한 풀이
```
const solution = numbers => {
const firstMax = Math.max(...numbers);
const filteredArr = numbers.filter(ele => ele !== firstMax);
const secondMax = Math.max(...filteredArr);
return firstMax * secondMax;
```

> 위와 같이 풀어 제출하니 반은 통과했지만 반은 통과하지 못했다. 왜일까? 아마 같은 숫자가 나오는 경우를 생각하지 못해서 생긴 오류 같다. Max를 가져와야하는데 만약 같은 숫자가 여러개라면? 전체 수가 [1,1,1,1,1,1]이라면 결과값이 나올 수 가 없다. 다른 방법으로 풀어야 한다. 배열안의 수를 작은수부터 큰수로 sort시키고 마지막 두 수를 곱해주는것도 방법!

```
const solution = numbers => {
    const firstMax = numbers.sort((a,b)=>a-b).pop();
    const secondMax = numbers.pop();
    return firstMax*secondMax
}
```

> 통과했다! 다른사람의 풀이를 보니 비슷하게 푼것 같은데 정말 간단하게 푼 사람이 있어 공유한다.

```
function solution(numbers) {
    numbers.sort((a,b)=>b-a);
    return numbers[0]*numbers[1];
}
```

> 큰 수에서 작은 수로 정렬시킨 후, 첫번째와 두번째 인자를 곱해주는 방식이다. 간단하면서 멋있다. 왜 저렇게 생각하지 못했을까? ㅋㅋㅋ 다음번엔 저렇게 풀어봐야지!