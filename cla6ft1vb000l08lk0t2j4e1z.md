# [JavaScript] 문자열 정렬하기 (1) (Sorting strings 1)

# 문제 설명
문자열 my_string이 매개변수로 주어질 때, my_string 안에 있는 숫자만 골라 오름차순 정렬한 리스트를 return 하도록 solution 함수를 작성해보세요.

# 제한사항
1 ≤ my_string의 길이 ≤ 100
my_string에는 숫자가 한 개 이상 포함되어 있습니다.
my_string은 영어 소문자 또는 0부터 9까지의 숫자로 이루어져 있습니다. - - -
# 입출력 예
<table>
<tr><th>my_string</th><th>result</th></tr>
<tr><td>"hi12392"</td><td>[1, 2, 2, 3, 9]</td></tr>
<tr><td>"p2o4i8gj2"</td><td>[2, 2, 4, 8]</td></tr>
<tr><td>"abcde0"</td><td>[0]</td></tr>
</table>
	
# 입출력 예 설명
**입출력 예 #1**

- "hi12392"에 있는 숫자 1, 2, 3, 9, 2를 오름차순 정렬한 [1, 2, 2, 3, 9]를 return 합니다.

**입출력 예 #2**

- "p2o4i8gj2"에 있는 숫자 2, 4, 8, 2를 오름차순 정렬한 [2, 2, 4, 8]을 return 합니다.

**입출력 예 #3**

- "abcde0"에 있는 숫자 0을 오름차순 정렬한 [0]을 return 합니다.

# 나의 풀이

```
const solution = my_string => my_string.split('').map(Number).filter(ele=>!isNaN(ele)).sort((a,b) => a-b)
```

> 문제는 간단했다. string을 split을 활용해 array화 시키고 map으로 Number화 시키면 characters는 NaN으로 출력된다. NaN인 부분을 제외한 Numbers만 filter하여 sort로 오름차순으로 정렬하면 끝! 내가 막혔던 부분은 어떻게 NaN을 filter에서 제외하는가 였다. 처음엔 그냥 `array.filter(ele => ele !==NaN)` 으로 풀어봤지만 filter가 제대로 동작하지 않았다. Google에 검색해 보니, isNaN을 사용하면 된다고 하여 바로 적용! 문제풀이 성공! 

> The **isNaN()** function determines whether a value is NaN or not. Because coercion inside the isNaN function can be surprising, you may alternatively want to use Number.isNaN().

[👉 isNaN() - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN)