# [1st project] TabomGalagsin  #01 🩴

# 1st day of the project

우리가 클론 할 website!! : [https://havaianas.com.br/](https://havaianas.com.br/)

## 초기세팅 git clone 받기!

- 오전에 어제 팀원들과 진행한 초기세팅한 main을 github을 통해 clone받고 내가 맡은 분야인 navbar 구현을 진행했다.

## Sprint standup meeting

- 팀원들과 첫 standup meeting을 진행했다. 백엔드, 프론트엔드 어제한 일, 오늘할 일 그리고 blocker을 공유하였다. 나는 navbar에 추가할 우리팀 로고를 만들어 보여주었다. 다행히 마음에 들어하셔서 로고로 추가하기러 했다.

## Navbar 구현 시작!

- 일단 clone할 website를 보며 구조를 잡았다. 상단메뉴가 여러가지였는데 그 중 카테고리부분만 일단 클론하게 되어 상단 메뉴바의 구조를 살짝 수정했다. Navbar은 2개로 나누었고 (메뉴바 위에 carousel 광고기능을 위해) flex를 사용하여 각 아이콘과 로고의 position을 잡아주었고 navbar는 2개로 나누었다.
- 처음엔 공식웹사이트의 메인 colour을 넣었지만 화면이 바뀔 때마다 배경화면과 nav bar도 같이 바뀌는걸 보고 `background: none`으로 수정, 그리고 `box-shadow: 0px 8px 15px rgb(0 0 0 / 10%)` 넣어주어 메인 배경색과 구분이 가도록 한 것을 클론하였다.
- CSS hover기능을 사용해서 메뉴를 마우스로 hover했을 때 dropdown 메뉴가 뜨게 하고 싶었는데 아무래도 아이콘과 nesting이 되지 않은 `<div>`여서 적용이 되지 않았다. 어떻게 하면 dropdown 메뉴가 뜰 수 있을지 고민 해 보았다. 앞서 배운 useState를 사용해서 초기값을 false로 설정하고 addEventListener onMouseOver(또는 onMouseEnter)을 사용하여  마우스를 갖다 댔을 때, 메뉴 dropdown메뉴가 navbar하단에 생기게 하고 onMouseLeave을 써서 마우스가 dropdown메뉴와 아이콘을 벗어나면 다시 그 메뉴가 사라지게 만들 수 있었다! 하지만 여기서 또 문제가 생겼다. 같은기능을 하는 이 useState를 child component에도 사용하고 싶었는데 그렇게 되니 true와 false가 섞여버려 렌더링이 안되는 문제가 생겼다.
- 같은 팀원분께 SOS를 요청했더니 각컴포넌트별로 useState를 따로 줘서 섞이지 않게 해야한다고 하셨다. 그리고 코드를 수정해주셨는데 훨씬 코드가 짧아졌고 제 기능도 구현이 되었다.

```jsx
import React, { useState } from 'react';
import DropdownContent from './DropdownContent/DropdownContent';
import './Dropdown.scss';

function Dropdown({ onMouseLeave }) {
  const [menuMouseEnter, setMenuMouseEnter] = useState('Categories'); // true false 대신 메뉴 이름 사용

  return (
    <div className="Dropdown" onMouseLeave={onMouseLeave}> // 마우스가 div를 떠났을 때 드롭다운을 없애라
      <div className="dropdownMenu">
        <div className="dropdownCategory">
          <ul>
            <li
              className="arrow"
              onMouseOver={() => {
                setMenuMouseEnter('Categories'); // arrow function으로 변수를 수정
              }}
            > // 카테고리를 hover했을 때, 카테고리가 나타나게
              Categories <i className="fa-solid fa-angle-right arrow" />
            </li>
            <li
              className="arrow"
              onMouseOver={() => {
                setMenuMouseEnter('Colour');
              }}
            > // colour를 hover 했을 때, colour가 나타나게
              Colour <i className="fa-solid fa-angle-right arrow" />
            </li>
          </ul>
        </div>
        <DropdownContent title={menuMouseEnter} /> // 이 컴포넌트 안에 있는 타이틀 별로 내용 변경
      </div>
    </div>
  );
}

export default Dropdown;
```

- `<DropdownContent>`는 재사용하였다. → 같은 format 안에 다른 내용

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660975959146/7_YjM6uq8.png align="left")


---
# My thoughts
<aside>
💡 드디어 내 생의 첫 1차 프로젝트가 시작되었고 FE,BE 팀원들이 정해졌다.
내가 제안했던 웹사이트를 하게 되서 초큼 부담스럽긴 했지만 그래도 멋있게 구현하고싶다!
팀명이름을 정했는데 너무 웃기닼ㅋㅋㅋ havaianas를 클론하기로 해서 쪼리에 관련된 조이름을 짓고싶었는데
쪼리는 아무래도 일본어라 쪼리를 한국어로 찾아보니 가락신 이였다 ㅋㅋㅋㅋ 거기에 브라질 브랜드라서 브라질어+한국인들이 아는 단어인 "따봉"을 사용해서 `따봉 가락신`이 되었다 ㅋㅋㅋㅋㅋㅋㅋ 이름 참 잘 지은듯!!! 
</aside>