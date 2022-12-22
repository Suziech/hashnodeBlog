# [JavaScript] 이상한 문자 만들기 (Making Strange Texts)

# 문제 설명
- 문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요.

# 제한 사항
- 문자열 전체의 짝/홀수 인덱스가 아니라, 단어(공백을 기준)별로 짝/홀수 인덱스를 판단해야합니다.
첫 번째 글자는 0번째 인덱스로 보아 짝수번째 알파벳으로 처리해야 합니다.

#입출력 예
<table>
<tr><th>s</th><th>return</th></tr>
<tr><td>"try hello world"</td><td>"TrY HeLlO WoRlD"</td></tr>
</table>

# 입출력 예 설명
- "try hello world"는 세 단어 "try", "hello", "world"로 구성되어 있습니다. 각 단어의 짝수번째 문자를 대문자로, 홀수번째 문자를 소문자로 바꾸면 "TrY", "HeLlO", "WoRlD"입니다. 따라서 "TrY HeLlO WoRlD" 를 리턴합니다.

> 이 문제 계속 잘 안풀려서 엄청 스트레스 받았다. 처음엔 쉽게 풀었는데 다른 테스트케이스에서 계속 막혀서 풀지 못했다. 

# 풀이

```
const solution = s => {
    const splittedArr = s.split(' ').map(ele => ele.split(''));
    let result = [];
    for(let i=0; i<splittedArr.length; i++) {
        for(let j=0; j<splittedArr[i].length; j++){
            splittedArr[i][j] = j%2 ? splittedArr[i][j].toLowerCase() : splittedArr[i][j].toUpperCase()
        }
        result.push(splittedArr[i].join(''))
    }
    return result.join(' ')
}
```

> 일단 splittedArr에 문자열 s를 split한 후, 이중배열안에 넣어준다. 빈 배열 result를 선언하고 for문을 두번 돌려 배열속 splittedArr[i][j]의 값을 index에 따라 대소문자로 바꿔준다. 결과(splittedArr[i]를 빈배열 result에 push해준 후 join으로 합쳐준다.  그리고 return에 join으로 한번 더 합쳐준다.

> 정말 피곤한 문제풀이였다. 나중에 한번 더 풀면 과연 가능할까 ㅠㅠ 그래도 계속 반복하다 보면 나아질꺼다!!!