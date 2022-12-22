# [JavaScript] 약수의 개수와 덧셈 (the number of divisor)

# 문제 설명
- 두 정수 left와 right가 매개변수로 주어집니다. left부터 right까지의 모든 수들 중에서, 약수의 개수가 짝수인 수는 더하고, 약수의 개수가 홀수인 수는 뺀 수를 return 하도록 solution 함수를 완성해주세요.

# 제한사항
- 1 ≤ left ≤ right ≤ 1,000
# 입출력 예
<table>
<tr><th>left</th><th>right</th><th>result</th></tr>
<tr><td>13</td><td>17</td><td>43</td></tr>
<tr><td>24</td><td>27</td><td>52</td></tr>
</table>

# 입출력 예 설명
**입출력 예 #1**

- 다음 표는 13부터 17까지의 수들의 약수를 모두 나타낸 것입니다.

<table>
<tr><th>수</th><th>약수</th><th>약수의 개수</th></tr>
<tr><td>13</td><td>1, 13</td><td>2</td></tr>
<tr><td>14</td><td>1, 2, 7, 14</td><td>4</td></tr>
<tr><td>15</td><td>1, 3, 5, 15</td><td>4</td></tr>
<tr><td>16</td><td>1, 2, 4, 8, 16</td><td>5</td></tr>
<tr><td>17</td><td>1, 17</td><td>2</td></tr>
</table>

- 따라서, 13 + 14 + 15 - 16 + 17 = 43을 return 해야 합니다.

**입출력 예 #2**

- 다음 표는 24부터 27까지의 수들의 약수를 모두 나타낸 것입니다.

<table>
<tr><th>수</th><th>약수</th><th>약수의 개수</th></tr>
<tr><td>24</td><td>1, 2, 3, 4, 6, 8, 12, 24</td><td>8</td></tr>
<tr><td>25</td><td>1, 5, 25</td><td>3</td></tr>
<tr><td>26</td><td>1, 2, 13, 26</td><td>4</td></tr>
<tr><td>27</td><td>1, 3, 9, 27</td><td>4</td></tr>
</table>

- 따라서, 24 - 25 + 26 + 27 = 52를 return 해야 합니다.

> 이거 쉽지 않았다. for를 두번 돌려서 약수를 구해서 짝수면 +1 홀수면 -1을 곱해주려고 했는데 마음대로 되지 않았다. 그러다가 <mark>제곱근의 약수는 홀수</mark>라는 좋은 소식을 접수! 바로 진행했고 문제를 풀 수 있었다.
left와 right 를 기준으로 for을 돌리고 `Math.sqrt()`를 이용해서 제곱근을 구했고 구한 제곱근의 Math.floor(내림)과 같다면, 즉 둘다 정수라면 *-1 아니라면 *+1을 한 후 나온 값을 다 더해주는 방식으로 진행했다.

# 나의 풀이

```
function solution(left, right) {
let count = 0;
    for(let i=left; i<right+1; i++){
       Math.sqrt(i) === Math.floor(Math.sqrt(i))?
         count += i*-1: count += i*1;
    }
    return count;
}
```