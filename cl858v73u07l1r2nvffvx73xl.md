# [JavaScript] 평균구하기

# 문제 설명
정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

# 제한사항
arr은 길이 1 이상, 100 이하인 배열입니다.
arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.
# 입출력 예
<table>
<tr><th>arr</th><th>return</th></tr>
<tr><td>[1,2,3,4]</td><td>2.5</td>
<tr><td>[5,5]</td><td>5</td>
</table>

> 배열의 합을 먼저 구하기에서 저번에 사용했던 reduce()가 바로 생각이 났고 바로 적용했다. 그리고 평균을 구하기 위해 array의 length를 구해서 나누어주니 바로 정답!!! 반복학습의 중요성을 느꼈다 🤓 

# 나의 풀이
```
function solution(arr) {
return arr.reduce((prev,curr) => prev+curr)/arr.length
}
```

