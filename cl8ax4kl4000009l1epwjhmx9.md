# [JavaScript] 문자열 내 p와 y의 개수m

# 문제 설명
대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

## 제한사항
문자열 s의 길이 : 50 이하의 자연수
문자열 s는 알파벳으로만 이루어져 있습니다.
## 입출력 예
<table>
<tr><th>s</th><th>answer</th></tr>
<tr><td>"pPoooyY"</td><td>true</td></tr>
<tr><td>"Pyy"</td><td>false</td></tr>
</table>
	
## 입출력 예 설명
### 입출력 예 #1
'p'의 개수 2개, 'y'의 개수 2개로 같으므로 true를 return 합니다.

### 입출력 예 #2
'p'의 개수 1개, 'y'의 개수 2개로 다르므로 false를 return 합니다.

> 매일매일 점점 흥미로워지는 문제들!!! ㅋㅋㅋ 일단 대소문자는 상관없다고 하니 모든 문자를 case가 같게 만들기 위해 나는 소문자를 선택했다! toLowerCase()로 전체 소문자로 변환, 그 후, split()을 이용해서 배열안에 알파벳 하나씩 넣어주고 `p`와 `y`의 상수를 만든 후, 각각 filter()와 includes()[ => `p`를 포함하는가? 또는 `y`를 포함하는가? ]그리고 length를 이용해 갯수를 구해 서로 비교하여 갯수가 같으면 true, 다르면 false가 나오게 설정했다.

# 나의 풀이
```
function solution(s){
    const arr = s.toLowerCase().split('')
    const p = arr.filter(el=>el.includes('p')).length
    const y = arr.filter(el=>el.includes('y')).length
    
    return p === y && true
}
```

> 결과는 통과! 통과 후 다른사람들의 풀이를 봤는데 보자마자 '와우'를 외쳤다!

# 다른사람의 풀이
```
function numPY(s){
    return s.toUpperCase().split("P").length === s.toUpperCase().split("Y").length;
}
```

> 간단하면서도 신박하다. P를 기준으로 나눈것 그리고 Y를 기준으로 나눈것의 길이로 비교! 어짜피 문자는 같은걸 공유하기 때문에 p의 길이와 y의 길이가 같다는것은 갯수가 같다는 것!


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1663721898686/GzvmVkaNe.png align="left")
