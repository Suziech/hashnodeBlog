# [JavaScript] for 문

for문을 사용하면 코드를 원하는 만큼 반복시킬 수 있다.

# Quiz) findSmallestElement 함수를 구현해 주세요.

- findSmallestElement 의 arr 인자는 숫자 값으로만 이루어진 배열입니다.
- arr 의 값들 중 가장 작은 값을 리턴 해주세요.
- 만일 arr 가 비어있으면 0을 리턴 해주세요.

- 예를 들어, 다음과 같은 배열이 인자(input)으로 들어왔다면 1이 리턴 되어야 합니다.
> [20, 200, 23, 1, 3, 9]

my answer)
❌ - fail
```
const findSmallestElement = arr => {
      for(let i = 0; i < arr.length; i++){
        if(arr[i] < arr([i+1]) {
          return arr[i];
        else if(length.arr === 0){
          return 0
      }
```

숫자를 대입해 봐도 이건 답이 나올 수 없는 구조. 하지만 어떻게 풀어야 하는지 감이 잡히지 않았다.
어떻게 해야할까 고민하던 중 hint를 얻게 되었다. 바로 첫번째 수와 비교하는 변수를 만들고 만약 첫번째 수보다 두번째 수가 작다면 더 작은 수를 변수에 다시 넣어 그 다음 수와 비교하는 방법! 바로 시도 해 보았다.<br>

✅ - pass
```
const findSmallestElement = arr => {
  if(arr.length === 0) {
    return 0;
  } 

  let smallest = arr[0]
    for(let i = 0; i < arr.length; i++){
      if(arr[i] < smallest){
        smallest = arr[i];
      }}
      return smallest;
    }
```

성공!  for loop을 돌면서 제일 작은 수가 smallest 로 들어가게 되고 계속 비교하다가 결국 제일 작은 수가 남게 된다.