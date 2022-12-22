# [JavaScript] object

# Assignment
아래 설명을 읽고 `getExamResult` 함수를 구현하세요.
인자 `scores` 는 다음과 같은 객체입니다. 객체의 요소의 갯수 및 키의 이름들은 달라질 수 있습니다. 객체의 값은 다음 9가지 문자열 중에서 하나를 가지고 있습니다.

- 'A+', 'A', 'B+', 'B', 'C+', 'C', 'D+', 'D', 'F
```
{
  '생활속의회계': 'C',
  '논리적글쓰기': 'B',
  '독일문화의이해': 'B+',
  '기초수학': 'D+',
  '영어회화': 'C+',
  '인지발달심리학': 'A+',
}
```
인자 `requiredClasses` 는 다음과 같이 문자열로 된 배열입니다.
```
['영어회화', '기초수학', '공학수학', '컴퓨터과학개론']
```
다음 조건을 만족하는 객체를 리턴하도록 함수를 구현해주세요.

`scores` 객체가 가지고 있는 키들은 새로운 객체에 포함되어야 합니다. 단, 그 값들은 다음 원리에 따라 숫자로 바뀌어 할당되어야 합니다.

A+ => 4.5 /
A => 4 /
B+ => 3.5 /
B => 3 /
C+ => 2.5 /
C => 2 /
D+ => 1.5 /
D => 1 /
F => 0

`requiredClasses` 배열의 요소로는 존재하지만, `scores`의 키로는 존재하지 않는 항목이 있다면, 해당 요소는 새로운 객체의 키가 되고, 값으로 0을 가져야 합니다. 위에서 예시로 묘사된 객체와 배열이 인자로 들어왔다면, 다음과 같은 객체과 리턴됩니다. 요소간 순서는 다를수 있지만, 채점에 무관합니다.

```
{
  '생활속의회계': 2,
  '논리적글쓰기': 3,
  '독일문화의이해': 3.5,
  '기초수학': 1.5,
  '영어회화': 2.5,
  '인지발달심리학': 4.5,
  '공학수학': 0,
  '컴퓨터과학개론': 0,
}
```
> 엄청 헤맸던 문제! 혼자서는 너무 힘들어 여기저기 도움을 구했고 결국 풀었다 🥲 

# 문제풀이 과정

문제를 풀기도 전에 어떻게 풀어야 할지 감도 잡히지 않았다.
사실 알파벳으로 된 점수를 숫자로 변경하는 아주 간단한 일이였는데도 뭘 어떻게 풀어야 할지 몰랐다.

JavaScript에서 데이터 전달 방식이 어떻게 되는지를 먼저 이해 해야했다. 

그리고 나서 object(객체)의 [key]값을 변경 해 주는 방법을 생각 해 보아야 한다.

1. 우선 변경하고 싶은 object를 생성 해 준다.
```
  const point {
        'A+': 4.5,
        'A': 4,
        'B+': 3.5,
        'B': 3,
        'C+': 2.5,
        'C': 2,
        'D+': 1.5,
        'D': 1,
        'F': 0
  };
```
2. for-in을 사용하여 반복문을 만들고(object 순회) 순회하며 1차적으로 scores에 있는 value들을 잠시 다른 변수에 넣어준다. 그리고 point에 있는 value값을 넣어준다.<br/>
쉽게 설명하자면, <br/>
  -> `const temp = scores[score];` 을 실행하면, score의 value값이 temp 변수에 저장된다. (value : 2, 3, 3.5 ...)<br/>
 -> `scores[key = point[temp]` 을 실행하면 score의 value값에 point의 value값이 저장, 업데이트 된다.
```
for(let score in scores){
      const temp = scores[score];
       scores[key] = point[temp];
```

3. 위의 과정을 거치면 `console.log(scores);`를 출력 했을 때, 아래와 같이 나온다.
```
const scores = {
  '기초수학': 1.5,
  '논리적글쓰기': 3,
  '독일문화의이해': 3.5,
  '생활속의회계': 2,
  '영어회화': 2.5,
  '인지발달심리학': 4.5
}
```

첫번째 조건 완료! 이제 마지막 조건을 풀어보자.

requiredClasses의 array가 scores의 object에 존재하지 않는다면 그 과목을 scores에 넣어주고 value값을 0으로 주어야 한다.

4. for-of를 사용해서 해결이 가능하다. test를 해보니 for-of는 array에서만 가능한 것 같다.
```
for(let key of requiredClasses){
  if(!scores[key]) {
      scores[key] = 0;
    }
```
> const requiredClasses= ['영어회화', '기초수학', '공학수학', '컴퓨터과학개론']

해석 해 보면, 만약 `scores[key]`가 아니라면(!)

대입해보면, scores[영어회화] = 2.5라는 값이 나온다. 
위의 값은 scores에 존재하기 때문에 false처리되어 무시된다.

'공학수학'의 경우 scores에 존재하지 않기 때문에 true를 반환. 조건문이 실행된다.
scores['공학수학'] = 0 을 해주면 scores의 object에 추가된다.

결국 object안에 존재하지 않는 key와 value(0)가 입력되는 것.

성공!! 🥳
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659054421403/9VA4ul9Ci.png align="left")

# takeaway
It was not an easy quiz and I can say it was the most difficult one through the session I had recently. I actually tried twice before and I've decided to blog it to remember how I solved. it was my third time to solve but I couldn't do it without seeing the answer I wrote last time.
I've got to try again maybe after three days to see if I still can remember the solve.
I will try until I can fully remember the solution perfectly ‼️

p.s. I also didn't remember how the object look like. let's repeat and repeat again 👩‍💻🤓