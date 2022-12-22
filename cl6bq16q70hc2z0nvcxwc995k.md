# [React] Router & Sass

# SPA & Routing

## Routing

- react is not a framework so routing function is not included.
- therefore, need to install the separated library for the routing function.
- diffrent from html, react use only one page(html) and we call this "SPA"(Single Page Application). if I want to show other page, I would link another page using `<a>` tag. but since react has only one html, need to use routing function.

## SPA

- SPA stands for Sinle Page Application. 
- Page means 'HTML'
- the opposite one would be MPA(Multi Page Application -> linked by html to another html)
- SPA needs routing function to show another page(to draw another page in the same html)


## React-Router

- it's the most used library in React for routing.
```
$ npm install react-router-dom
```

- once you type the above in the terminal from the directory of your project file, you can install.
- after the install, you can check if it was well installed from `dependencies` in `package.json`
- to execute, need to make an folder "Router.js" in src first
- and need to import **BrowserRouter, Routes, Route** components

```
import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';
```

the below is how to code for router.js file.

```
// Router.js

import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';

const Router = () => {
  return (
    <BrowserRouter>                                  // 1                               
      <Routes>                                       // 2                            
        <Route path="/" element={<Components />} />  // 3
      </Routes>
    </BrowserRouter>
  );
};

export default Router;
```

- what would be the role for the **BrowserRouter, Routes, Route** components?
	- `BrowserRouter` : it has the function of being able to change address without being refreshed
	- `Routes` : it renders only one route which matches the rule.
	- `Route` : it sets the rules.
		- it has two properties (path & element)
			- path: sets the route
			- element : decides which component to show when it follows the path.

```
// Router.js

import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import Login from './pages/Login/Login';                    ⌉
import Signup from './pages/Signup/Signup';                 ⎮ // 1
import Main from './pages/Main/Main';                       ⌋

const Router = () => {
  return (
    <BrowserRouter>
      <Routes>
        <Route path='/' element={<Login />} />              ⌉
        <Route path='/signup' element={<Signup />} >        ⎮ // 2
        <Route path='/main' element={<Main />} />           ⌋
      </Routes>
    </BrowserRouter>
 );
};

export default Router;
```

- sometimes, you may encounter loads of websites which has same Nav and Footer. how to we do that? thoses are needed to be refreshed all the times whenever user changes the pages?
- NO. it's a double job to do that. there's why to fix in that kind of situation.

- for this, Nav and Footer can be located outside of `Routes` as below.

```
// Router.js

import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import Nav from './components/Nav/Nav';
import Footer from './components/Footer/Footer';
import Login from './pages/Login/Login';
import Signup from './pages/Signup/Signup';
import Main from './pages/Main/Main';

const Router = () => {
  return (
    <BrowserRouter>
      <Nav />                                          // nav 컴포넌트
      <Routes>
        <Route path="/" element={<Login />} />
        <Route path="/signup" element={<Signup />} />
        <Route path="/main" element={<Main />} />
      </Routes>
      <Footer />                                       // footer 컴포넌트
    </BrowserRouter>
  );
};

export default Router;
```

- How do we render the different page views by clicking buttons?
- there are 2 ways to make it happens
- 1. Using `<Link>` component
- 2. Using useNavigate hook

- Actually, when you see the source code via dev tools, you will see the link component showing as `<a>` tag
- then why do we need to use the component?
- if we use `<a>`tag, it requests a whole new page even though only some parts are needed to be changed. in this case, if we use the component, it will be more efficient since it will change only the part needed to be changed

- BUT!! there are some cases you need to use `<a>` 
- if you embed or connect to the website from outside, yes, you need to use `<a>`

### using `<Link>` component

```
// Login.js

import React from 'react';
import { Link } from 'react-router-dom';

const Login = () => {
  return <Link to="/signup">회원가입</Link>;
};

export default Login;
```

### using useNavigate hook

```
// Login.js

import React from 'react';
import { useNavigate } from 'react-router-dom';       // 1

const Login = () => {
  const navigate = useNavigate();                     // 2

  const goToMain = () => {                            // 3
    navigate('/main');
  };

  return (
    <button className="loginBtn" onClick={goToMain}>  // 4
      로그인
    </button>
  );
};

export default Login;

```

- what's the differences between `hook` $ `link`?
- it's very easy, `<Link>` just takes you to the new component
- `hook` is different, you can give some condition to use the button
- for example, if ID and PW are not matched, the button won't work.

> to sum up, it's better to use `<Link>` if it's Nav bar or Aside menu.
and for `hook`, you can use if there's conditions (ID/PW)

# Sass [CSS Preprocessor]

## 1. CSS Preprocessor

- it came out due to complexity of using CSS
- one of the CSS preprocessor is `SASS`

## 2. Sass

- install Sass
```
$ npm install sass
```

- after installing, you can check the result @ dependencies in package.json


- since there's only one HTML in React, CSS File might be clashed there fore Sass has been created!

- you can give a className to the top one with the same name as component

: variable\
: & selector\
: mixin

### `@mixin` 과 `@extend`의 차이점
- extend는 연관된 요소에 사용해주고 mixin은 연관되지 않아도 사용 해 줄 수 있다.
- mixin은 예를들면 flex요소를 다른 div들에게 지정해 줄때

### component 확장자명 `js` vs `jsx`?
- jsx는 typescript에 사용하는 확장자명이다.

### common.scss는 어디에 위치하는게 좋을까?
- 모든 component에 적용되어야 하므로 index.js에 import 해주면 좋다.

### import 순서에 따라 css의 우선순위가 달라질 수 있다.