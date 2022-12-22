# [javaScript] 나누어 떨어지는 숫자 배열 (divisor)

# 문제 설명
array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.
divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

# 제한사항
arr은 자연수를 담은 배열입니다.
정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.
divisor는 자연수입니다.
array는 길이 1 이상인 배열입니다.
## 입출력 예
<table>
<tr><th>arr</th><th>divisor</th><th>return</th></tr>
<tr><td>[5, 9, 7, 10]</td><td>5</td><<td>[5, 10]</td>/tr>
<tr><td>[2, 36, 1, 3]</td><td>1</td><<td>[1, 2, 3, 36]</td>/tr>
<tr><td>[3,2,6]</td><td>10</td><<td>[-1]</td>/tr>
</table>
		
### 입출력 예 설명
- 입출력 예#1
arr의 원소 중 5로 나누어 떨어지는 원소는 5와 10입니다. 따라서 [5, 10]을 리턴합니다.

- 입출력 예#2
arr의 모든 원소는 1으로 나누어 떨어집니다. 원소를 오름차순으로 정렬해 [1, 2, 3, 36]을 리턴합니다.

- 입출력 예#3
3, 2, 6은 10으로 나누어 떨어지지 않습니다. 나누어 떨어지는 원소가 없으므로 [-1]을 리턴합니다.

> 와 이거 때문에 30분만 해야하는데 1시간이나.... 왜 안되지... 원인파악을 하고 좀더 로지컬하게 다가가봐야할 것 같다.
for loop을 돌렸을 때, return하면 for문에 종료되는것과 연관이 있는 것 같다. 이걸 해결하기 위해서는 어떻게 해야할까?

```
const solution = (arr, divisor) => {
        const result=[];
    for(let i=0; i<arr.length; i++){

        if(arr[i]%divisor===0) {
            result.push(arr[i])
        }
    }
    return result;
}

```

> ㅋㅋㅋㅋㅋ 하루 자고나면 풀리는 문제는 너무 신기하다 ! 같은 뇌로 고민하는건데 이렇게 다를수가 ㅠㅠ 

# 나의 풀이
```
const solution = (arr, divisor) => {
const result = [];
  for(let i=0; i<arr.length; i++){
    arr[i]%divisor===0 && result.push(arr[i])
  }
  return result.length>0 ? result.sort((a,b)=> a-b) : [-1]
}
```

> 어제와 형식은 비슷. 하지만 오늘은 sort((a,b)=>a-b)로 오름차준으로 정렬시켜주고 답을 길이로 판단해서 0보다 작으면  `[-1]`을 return해 주는 방법으로 풀었다!