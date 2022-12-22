# [React] Side Effect

# Side Effect

부작용 = 부수적으로 발생하는 효과

코딩의 세계에서의 부작용
1. 코드가 의도한 주된 효과 외에 추가적으로 발생하는 효과
2. 함수에서 자주 사용되는 용어
	- 함수의 본질적인 역할
		- Input을 받아서 Output을 산출 ( input => output )
	- 함수의 side effect는?
		- (input => output)이외의 모든 행위

```
const sum = (x) => {
return x+1;
};

// get x(input) and return x+1(output)
```

> input을 받아서 output을 내는 행위 외에 다른 행위를 하지 않음, 즉 Side Effect가 없음  : 순수함수

```
const num = 1;

const sum = (x) => {
return x + num;
};

// get x(input) and return x + num(output)
```
> 함수 외부의 값인 num을 읽어오고있기 때문에 side effect가 있다.

- 즉, 함수가 함수 내부의 값을 제외한 나머지 값들을 읽어올 때 "Side Effect가 있다" 라고 표현

```
let num;

const sum = (x) => {
num = x + 1;
};

// get x(input) and change num to x+1
```
> 이 함수는 Side Effect가 있다. 함수 내부의 값이 아닌 외부의 값인 "num"을 읽어오고 변경시키기 때문

```
const printNum = (x) => {
console.log(x);
};

const changeTitle = (newTitle) => {
const title = document.getElementById('title');

title.innerText = newTitle;
}
```

> 위의 두 함수들도 Side Effect를 가지고 있다. DOM 조작, 콘솔패널 문자 출력행위 또한 외부에 존재하는 DOM, 콘솔의 상태를 변경시키는 것이기 때문

- Programming에서 Side Effect란?

	- 1. 함수에서 함수 외부의 값을 읽어오는 행위
	- 	2. 함수에서 함수 외부의 값을 변경하는 행위

- Programming에서 Side Effect는 기피해야 할까?
	- yes, 기피해야한다.
	- why? side effect가 있는 함수는 동작결과를 예측하기 쉽지 않아서
		- 예를 들면, `const sum=(x)=>x+1`에서 x가 1인경우 x값을 쉽게 유추할 수 있지만, `const sum=(x)=>x+num`은 x를 유추하기 어려움
	- 함수의 결과를 예측할 수 없으면 프로그램의 동작을 예측하기 힘들어지고, 이는 곧 유지보수의 어려움을 야기.
	- 하지만 side effect를 피하는 것은 힘들다. 그러기에 개발자들은 side effect를 최소화 하는 방식으로 프로그램을 설계하고 만약 필요하다면 반드시 통제가능하게 만들어서 유지보수에 악영향을 주는것을 피해야 한다.
	
# React에서의 Side Effect

- 함수 컴포넌트의 input & output
	- React에서 rendering이란 state, props를 기반으로 UI를 그려내는 행위
	- UI를 component단위로 구성, 그 component들은 함수 component를 이용해 만들 수 있음
	- react 함수 컴포넌트의 본질? state와 props로 jsx를 만들어 내는 것
	- (state, props) => JSX

- 함수 컴포넌트의 Side Effect
	- state, props를 통해 jsx를 만들어내는 외의 모든 행위
	- 자주 일어나는 side effect
		- 1. Data Fetching
			- 프론트엔드가 백엔드 API(외부)를 통해서 필요한 데이터를 가져오는 행위 => side effect!!
		- 2. DOM 접근 및 조작
			- React에서 DOM을 조작하는것은 권장되지 않지만 특정상황에서 직접 DOM을 불러오는 행위는 => Side effect!!
		- 3. 구독(Subscribe)
			 - programming에서의 구독이란? 어떤 것을 계속 관찰하다가 변화가 발생하면 특정 엑션을 취함
			 - 보편적으로 '시간'을 구독함
			 - 특정 시간이 지났을 때, 특정 주기가 지났을 때 엑션을 취하는것은 시간을 구독함으로서 구현가능
			 - 실제 자바스크립트에서는 `setTimeout` : 특정시간이 지나면 동작 수행, `setInterval` : 일정시간마다 특정 동작을 수행 등의 메서드를 제공해줘서 쉽게 시간구동기능 제공
			 - 이 또한 외부의 값을 계속 관찰하고 거기에 맞춰 동작하므로 => Side effect!!

- React에서 Side Effect를 발생시키기 위한 조건
1. rendering을 blocking 하지 않기 위해서 **렌더링이 모두 완료되고 난 후에 실행할 수 있어야 함**
2. 매 rendering마다 실행되는 것이 아니라 **원할때만 조건부로 실행할 수 있어야 함**

위 조건을 충족시켜주기 위해 react에서는 `useEffect hook`을 제공해줌!

