# [React] Props & State

# Hook

> Hook = 갈고리 🪝

## 특징
- hook 은 class component에서만 사용할 수 있었던 state관리와 lifecycle관리기능을 function component에서도 사용할 수 있도록 hook in(연동) 해주는 function 을 의미하며, 이러한 hook들의 모음을 hooks라고 한다.

- `hook`은 class component에 있는 기능을 function component에서 사용하기 위해 나온 개념이기 때문에 **only function component**에서 사용 가능!

- hook의 이름은 반드시 `use-`로 시작
 
- React에서 제공하는 내장 hook이 존재 useState, useEffect ... )
-  내장 hook은 외부 library를 install하지 않아도 사용 가능

      - Customs hook : 직접 hook을 create


## 사용 규칙

1. hook을 호출할 수 있는 곳 -> function component 내부 & custom hook 내부
(위의 2 곳을 제외하고는 hook 호출 불가)

2. hook은 항상 function component 내의 **최상위at the top level)**에서만 호출해야함
(반복문, 조건문 등 중첩된 function 내에서는 hook 호출 불가)<br>
(function에서의 최상위)

```
// useState Hook을 최상위에서 호출
// Test.js

import React, { useState } from 'react';

const Test = () => {
  const [color, setColor] = useState('red');

  if (5 > 3) {
    console.log('true');
  }

  return <div>Hello!</div>;
};

export default Test;
```
# Props

> component의 속성값(property)<br>
 -> parent component로부터 전달받은 데이터를 지니고 있는 Object

- 전달하고자 하는 어떤 값이든 자식 컴포넌트에 전달 가능 <br>
-> text, number, variables, function

# State
> component내부에 가지고 있는 component의 상태값<br>
해당 component가 UI에 보여줄 정보를 결정할 때 사용할 수 있는 상태값<br>
component내에서 정의하고 사용하며 얼마든지 변경할 수 있다.

- useState의 첫 번째 요소인 `state` 를 통해 동적으로 관리하고자 하는 값을 할당할 수 있다.
- useState의 두 번째 요소인 `setState` 함수를 통해 `  state` 를 업데이트 할 수 있다.
