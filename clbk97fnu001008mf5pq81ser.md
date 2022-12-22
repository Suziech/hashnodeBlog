# [JavaScript] 2차원으로 만들기 (Make it 2-dementions)

###### **문제 설명**

정수 배열 `num_list`와 정수 `n`이 매개변수로 주어집니다. `num_list`를 다음 설명과 같이 2차원 배열로 바꿔 return하도록 solution 함수를 완성해주세요.

`num_list`가 \[1, 2, 3, 4, 5, 6, 7, 8\] 로 길이가 8이고 `n`이 2이므로 `num_list`를 2 \* 4 배열로 다음과 같이 변경합니다. 2차원으로 바꿀 때에는 num\_list의 원소들을 앞에서부터 n개씩 나눠 2차원 배열로 변경합니다.

| num\_list | n | result |
| --- | --- | --- |
| \[1, 2, 3, 4, 5, 6, 7, 8\] | 2 | \[\[1, 2\], \[3, 4\], \[5, 6\], \[7, 8\]\] |

* * *

##### 제한사항

*   `num_list`의 길이는 `n`의 배 수개입니다.
    
*   0 ≤ `num_list`의 길이 ≤ 150
    
*   2 ≤ `n` &lt; `num_list`의 길이
    

* * *

##### 입출력 예

| num\_list | n | result |
| --- | --- | --- |
| \[1, 2, 3, 4, 5, 6, 7, 8\] | 2 | \[\[1, 2\], \[3, 4\], \[5, 6\], \[7, 8\]\] |
| \[100, 95, 2, 4, 5, 6, 18, 33, 948\] | 3 | \[\[100, 95, 2\], \[4, 5, 6\], \[18, 33, 948\]\] |

* * *

##### 입출력 예 설명

입출력 예 #1

*   `num_list`가 \[1, 2, 3, 4, 5, 6, 7, 8\] 로 길이가 8이고 `n`이 2이므로 2 \* 4 배열로 변경한 \[\[1, 2\], \[3, 4\], \[5, 6\], \[7, 8\]\] 을 return합니다.
    

입출력 예 #2

*   `num_list`가 \[100, 95, 2, 4, 5, 6, 18, 33, 948\] 로 길이가 9이고 `n`이 3이므로 3 \* 3 배열로 변경한 \[\[100, 95, 2\], \[4, 5, 6\], \[18, 33, 948\]\] 을 return합니다.
    

> 3번정도 풀어봐도 볼때마다 어떻게 풀어야하는지 감이 잘 안잡히는 문제 😵‍💫
> 
> 여기서 가장 중요한 역할을 하는 splice에 대해 한번 더 정리 해 볼 필요가 있다!

## Array.prototype.slice()

The `slice()` method returns a shallow copy of a portion of an array <mark>into a new array </mark> object selected from start to end (end not included) where start and end represent the *index of items in that array*. The original array will not be modified.

```javascript
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2, 4));
// expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// expected output: Array ["bison", "camel", "duck", "elephant"]
```

slice()는 얕은 복사를 하며 (객체를 복사할 때 복사된 값이 같은 참조를 가리키고 있는 것, 원본 객체를 참조함) 시작값과 끝값 바로 앞의 인덱스까지 가지고와 새로운 어레이를 만들어 준다.

### 나의 풀이

```javascript
const solution = (num_list, n) => {
    let arr = [];
    for(let i=0; i<num_list.length/2; i++){
        arr = [...arr, num_list.slice(n*i, n*i+n)]
    }
    return arr;
}
```

`arr = [...arr]` 를 해주는 이유는 slice로 분할시킨 i번째 배열들을 다 불러오기 위해서 이다.

이부분이 아직도 좀 헷갈리지만.. 매일 풀다보면 언젠가 확 깨닫는 때가 오겠지 🥲