# [React] Props & State

# Hook

> Hook = ๊ฐ๊ณ ๋ฆฌ ๐ช

## ํน์ง
- hook ์ class component์์๋ง ์ฌ์ฉํ  ์ ์์๋ state๊ด๋ฆฌ์ lifecycle๊ด๋ฆฌ๊ธฐ๋ฅ์ function component์์๋ ์ฌ์ฉํ  ์ ์๋๋ก hook in(์ฐ๋) ํด์ฃผ๋ function ์ ์๋ฏธํ๋ฉฐ, ์ด๋ฌํ hook๋ค์ ๋ชจ์์ hooks๋ผ๊ณ  ํ๋ค.

- `hook`์ class component์ ์๋ ๊ธฐ๋ฅ์ function component์์ ์ฌ์ฉํ๊ธฐ ์ํด ๋์จ ๊ฐ๋์ด๊ธฐ ๋๋ฌธ์ **only function component**์์ ์ฌ์ฉ ๊ฐ๋ฅ!

- hook์ ์ด๋ฆ์ ๋ฐ๋์ `use-`๋ก ์์
 
- React์์ ์ ๊ณตํ๋ ๋ด์ฅ hook์ด ์กด์ฌ useState, useEffect ... )
-  ๋ด์ฅ hook์ ์ธ๋ถ library๋ฅผ installํ์ง ์์๋ ์ฌ์ฉ ๊ฐ๋ฅ

      - Customs hook : ์ง์  hook์ create


## ์ฌ์ฉ ๊ท์น

1. hook์ ํธ์ถํ  ์ ์๋ ๊ณณ -> function component ๋ด๋ถ & custom hook ๋ด๋ถ
(์์ 2 ๊ณณ์ ์ ์ธํ๊ณ ๋ hook ํธ์ถ ๋ถ๊ฐ)

2. hook์ ํญ์ function component ๋ด์ **์ต์์at the top level)**์์๋ง ํธ์ถํด์ผํจ
(๋ฐ๋ณต๋ฌธ, ์กฐ๊ฑด๋ฌธ ๋ฑ ์ค์ฒฉ๋ function ๋ด์์๋ hook ํธ์ถ ๋ถ๊ฐ)<br>
(function์์์ ์ต์์)

```
// useState Hook์ ์ต์์์์ ํธ์ถ
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

> component์ ์์ฑ๊ฐ(property)<br>
 -> parent component๋ก๋ถํฐ ์ ๋ฌ๋ฐ์ ๋ฐ์ดํฐ๋ฅผ ์ง๋๊ณ  ์๋ Object

- ์ ๋ฌํ๊ณ ์ ํ๋ ์ด๋ค ๊ฐ์ด๋  ์์ ์ปดํฌ๋ํธ์ ์ ๋ฌ ๊ฐ๋ฅ <br>
-> text, number, variables, function

# State
> component๋ด๋ถ์ ๊ฐ์ง๊ณ  ์๋ component์ ์ํ๊ฐ<br>
ํด๋น component๊ฐ UI์ ๋ณด์ฌ์ค ์ ๋ณด๋ฅผ ๊ฒฐ์ ํ  ๋ ์ฌ์ฉํ  ์ ์๋ ์ํ๊ฐ<br>
component๋ด์์ ์ ์ํ๊ณ  ์ฌ์ฉํ๋ฉฐ ์ผ๋ง๋ ์ง ๋ณ๊ฒฝํ  ์ ์๋ค.

- useState์ ์ฒซ ๋ฒ์งธ ์์์ธ `state` ๋ฅผ ํตํด ๋์ ์ผ๋ก ๊ด๋ฆฌํ๊ณ ์ ํ๋ ๊ฐ์ ํ ๋นํ  ์ ์๋ค.
- useState์ ๋ ๋ฒ์งธ ์์์ธ `setState` ํจ์๋ฅผ ํตํด `  state` ๋ฅผ ์๋ฐ์ดํธ ํ  ์ ์๋ค.
