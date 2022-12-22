# [JavaScript] 행렬의 덧셈

# 문제 설명
행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요.

# 제한 조건
행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.
# 입출력 예
```
arr1 = [[1,2],[2,3]]	
arr2 = [[3,4],[5,6]]
return [[4,6],[7,9]]
=============
arr1 = [[1],[2]]
arr2 = [[3],[4]]
return [[4],[6]]
```

> 매일 30분씩 프로그래머스 풀기를 하는데 이거 푸는데 한 3일 걸린 것 같다. 내가 처음에 풀었던 식은 아래와 같다.

```
arr1 = [[1,2],[2,3]]	
arr2 = [[3,4],[5,6]]

const result = [];

for(let i=0; i<arr1.length; i++){
  for(let j=0; j<arr1[i].length; j++){
    result.push(arr1[i][j]+arr1[i][j])
  }
}

console.log(result) // [4,6,7,9]
```

> 답에 근접한것 같지만 어떻게 `[[4,6],[7,9]]`를 만들어 내야하는지 도저히 생각이 나지 않았다. 하... 대괄호만 안에 넣어주면 되는데.... 결국 오늘 검색을 했고 ㅋㅋ 다른사람의 풀이를 보자마자 1초만에 꺼버렸다. 빈배열을 하나 더 넣어줘야 했던 것!! 평소에 문제 풀 때 배열을 두번 쓴 일이 많이 없어서 그런지 해결방법이 떠오르지 않았던 것 같다. 난 직접 그려보지 않으면 이해가 잘 가지 않아서 노트에 써서 하나씩 숫자를 대입해 보며 답을 도출해봤다. 1번째 index에서 계산한 값을 빈 배열에 넣어주고 result 배열에 또 push 해주어 배열안의 배열을 만들 수 있었다!! 통과!

```
arr1 = [[1,2],[2,3]]	
arr2 = [[3,4],[5,6]]

const result = [];

for(let i=0; i<arr1.length; i++){
const sum = [];
  for(let j=0; j<arr1[i].length; j++){
    sum.push(arr1[i][j]+arr1[i][j])
  }
result.push(sum);
}

console.log(result) // [[4,6],[7,9]]
```

요즘 프로젝트 하느라 정신이 없었지만 하루에 조금씩이라도 매일 하는게 중요한 것 같다.