# 1st Team Project retrospective : Tabom Galagsin

# 첫 Team Project의 시작!

## 👍 팀 명 : Tabom Galagsin (FE - 4 / BE - 2)
- 팀명은 팀원들과 의식의 흐름대로 짓게 되었는데, 일단 쪼리(ぞうり)가 일본어라 한국어로 쪼리가 무엇인지 찾아보니 '가락신' 이였고 브라질 브랜드였기 때문에 앞에 따봉(브라질어로 está bom = it's good)을 붙여 '따봉 가락신' 이 되었다. 😂 

## 📆 프로젝트 기간 
- `2022. Aug. 16 ~ 2022. Aug. 26` (11 days)

## 📝 프로젝트 설명 
- 슬리퍼로 유명한 Havaianas의 웹사이트를 클론 코딩 하였다. 웹사이트의 색상이 다양하고 화려하며 시도 해 보면 재미있는 기능들이 많이 있다. (ex. Carousel, Dropdown 등등)

### ✔️ 프로젝트를 통해 React를 배우며 느낀 점
- 초기에 React를 접했을 땐, `html` 과 비슷하게 생겨서 좋아했지만 새로운 기능을 접하면서 곧 vanilla JS가 더 쓰기 편하다고 느꼈다. 하지만 프로젝트를 진행하면서 점점 React만 사용하는 횟수가 많아지니 자연스럽게 React에 적응이 되기 시작했고 지금은 React가 Vanilla JS보다 사용하기 더 쉬우며 배우면 배울 수록 구현 할 수 있는 기능이 무궁무진하다고 생각한다. 아직도 갈 길은 멀지만 그래도 점점 React와 친해지는 중이다. React 고수가 되는 그날까지.. 🏃‍♀️
    
### ✔️ 혼자 할 때와 팀으로 진행할 때 다른 점 및 팀에서 내가 맡은 역할
- 프로젝트 이전에 혼자서 Instagram을 clone coding 했었다. 혼자서 할 때는 git을 통해 merge할 필요도 없고 conflict도 없어서 혼자 레고로 성을 짓는 느낌이였다. 하지만 팀원들과 함께 진행을 해보니 내가 맡은 역할을 잘 구현해서 merge 했을 때 문제가 생기지 않도록 해야 했다. 나의 로컬 컴퓨터에서는 아무런 문제가 없었던 Sass가 nesting이 잘못되어 다른 팀원들 각자의 로컬로 merge했을 때, 아웃라인 잡아놓은게 여기저기 다 튀어나갔고 동기들에게 체포당할 뻔했다.. 😅  이번 실수를 통해서 아무리 내 file에 문제가 없어도 다른 팀원들과의 협업을 위해서는 nesting이 정말 정말 중요하다는 걸 깨달았다!

- havaianas는 내가 제안 한 웹사이트여서 PM의 역할을 맡았다. 1차 sprint에서 초기에 프로젝트를 어떻게 진행할 것인지 그리고 누가 어떤 ticket을 받아갈 것인지를 정했고 매일 아침 standup meeting을 해서 어제 한 일, 오늘 한 일, 그리고 blocker를 서로 공유하면서 진행사항을 확인했다. 스케쥴 및 ticket관리는 `Trello`를 이용해 진행하였다.


- 프론트엔트 팀 안에서는 Navbar 및 제품 상세페이지를 맡았다.
    
### ✔️기억하고 싶은 코드

- **흐뭇한 코드 : Dropdown**
    
```
jsx
    <div
    		onMouseEnter={() => setIsMouseEnter(!isMouseEnter)}
        onMouseLeave={() => setIsMouseEnter(!isMouseEnter)}
       >
       <i className="fa-solid fa-bars navIcon menu" />
        {isMouseEnter && <Dropdown />}
    </div>
```

> Dropdown 메뉴를 구현한 코드! 마우스가 menu icon을 hover할 때 dropdown이 생겼지만 마우스가 떠나자마자 dropdown이 사라졌는데 이걸 어떻게 고치지 하고 고민하다가 발견한 방법! Icon과 dropdown을 한 `<div>`로 묶어 이 div에 `mouseEnter``mouseLeave`이벤트를 주면 된다. 새로운 방법을 알게 되서 흐뭇한 코드로 선정! 


![dropdown.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1661658398325/eKE0Bs1gZ.gif align="left")


- **신기했던 코드 : useState를 이용한 scroll event**
    
```
jsx
    const [scroll, setScroll] = useState(0);
    
      useEffect(() => {
        const handleScroll = e => setScroll(e.currentTarget.scrollY);
        window.addEventListener('scroll', handleScroll);
    
        return () => window.removeEventListener('scroll', handleScroll);
      });
    
      return (
        <nav
          className="nav"
          style={scroll < 32 ? { top: 0 - scroll } : { top: -32 }}
        >
    ```

> Navbar가 총 2개였는데 scroll down 했을 때 아래의 navbar만 상단에 fix되는 것을 구현. 처음 써보는 scroll event여서 어떻게 사용해야하는지 잘 몰랐었고 헤메었다. 스크롤 자체를 useState에 넣어주어 길이를 기준으로 postion:fixed 된 상단 navbar의 top을 변경해 주어 보이지 않게 하는 방법을 사용했다. 


![nav bar.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1661658871411/JrYweH3vu.gif align="left")

    
- ** 가장 어려웠던 코드 : useInterval(custom)을 이용한 carousel 구현**
        
<details>
<summary>코드보기</summary>

```
jsx
        import { useState } from 'react';
        import useInterval from '../../../useInterval';
        import './NavTopContainer.scss';
        
        function NavTopContainer() {
          const [currentPosition, setCurrentPosition] = useState(-2);
          const [transitionTime, setTransitionTime] = useState(0.5);
          const [resetAuto, setResetAuto] = useState(1);
        
          const currentData = [...CAROUSEL_DATA, ...CAROUSEL_DATA, ...CAROUSEL_DATA];
        
          const clickButton = event => {
            if (
              event.target.className !== 'fa-solid fa-chevron-left arrow flipflopCursor'
            ) {
              if (currentPosition > 2) {
                setTransitionTime(0);
                setCurrentPosition(-2);
                setTimeout(() => {
                  setTransitionTime(0.5);
                  setCurrentPosition(-1);
                }, 0);
              } else {
                setCurrentPosition(currentPosition + 1);
              }
            } else {
              if (currentPosition < -2) {
                setTransitionTime(0);
                setCurrentPosition(2);
                setTimeout(() => {
                  setTransitionTime(0.5);
                  setCurrentPosition(1);
                }, 0);
              } else {
                setCurrentPosition(currentPosition - 1);
              }
            }
          };
        
          useInterval(() => {
            if (currentPosition > 2) {
              setTransitionTime(0);
              setCurrentPosition(-2);
              setTimeout(() => {
                setTransitionTime(() => 0.5);
                setCurrentPosition(() => -1);
              }, 100);
            } else {
              setCurrentPosition(prev => prev + 1);
            }
          }, 3000 + resetAuto);
        
          return (
            <div className="navTopContainer">
              <div className="carousel">
                <div className="leftCover">
                  <i
                    className="fa-solid fa-chevron-left arrow flipflopCursor"
                    onClick={event => {
                      clickButton(event);
                      setResetAuto(prev => prev * -1);
                    }}
                  />
                </div>
                <div className="slider">
                  <div
                    className="sliderInner"
                    style={{
                      transform: `translate(${(currentPosition * -100) / 15}%)`,
                      transition: `all ${transitionTime}s`,
                    }}
                  >
                    {currentData.map((data, index) => {
                      return (
                        <section className="list" key={index}>
                          {data.item}
                        </section>
                      );
                    })}
                  </div>
                </div>
                <div className="rightCover">
                  <i
                    className="fa-solid fa-chevron-right arrow flipflopCursor"
                    onClick={event => {
                      clickButton(event);
                      setResetAuto(prev => prev * -1);
                    }}
                  />
                </div>
              </div>
            </div>
          );
        }
        
        export default NavTopContainer;
        
        const CAROUSEL_DATA = [
          { item: '상파울루시로 특급배송' },
          { item: '배송 옵션 및 서비스를 확인하려면 우편번호를 입력해 확인해 보세요.' },
          { item: '상파울루시로 특급배송' },
          { item: '배송 옵션 및 서비스를 확인하려면 우편번호를 입력해 확인해 보세요.' },
          { item: '따봉 가락신  화이팅!' },
        ];
```

> 이 코드는 진짜 두고두고 100% 이해할 때 까지 공부해야하는 코드! 최상단 Navbar에 사용된 carousel은 자동플레이가 되면서 동시에 화살표를 누르면 이동하는 기능을 한다 ( + 무한슬라이드까지!) 처음 carousel을 겨우겨우 만들었지만 화살표를 클릭하면 버튼기능과 자동플레이 기능이 겹치면서 두칸이 한번에 넘어가버렸다. 이를 방지하기 위해 custom으로 useInterval을 사용해서 넘어가는 속도가 reset하게 만들어 버튼기능을 실행해도 두장씩 넘어가지 않게 구현!

![carousel.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1661670339353/qjkEwaPqD.gif align="left")

</details>
- ** 새로 알게 된 코드 :  state 초기 값 없이 re-rendering 시켜주는 코드. 필요할 때 사용하면 유용할 것 같다. **
```
const setSelectColour = useState(0)[1];
```
## 💡 프로젝트를 마치고 느낀 점

- 개발공부를 시작한 이후로 해보는 첫 팀 프로젝트!! 기대반 걱정반으로 진행했는데 좋은 팀원들과 분위기로 으쌰으쌰 하며 웹사이트를 완성 해 나갔고 그 과정속에서 서로 소통하는 방법에 대해 더 생각해 보는 계기가 되었다. 내 머릿속에 있는 생각을 상대방이 이해할 수 있게 설명하는건 생각보다 어려웠고 더 많은 연습이 필요 할 것같다.
- 팀의 분위기가 프로젝트 전반적인 흐름을 주도하는 것 같다. 아무리 힘들고 지쳐도 긍정적으로 함께 이겨내자라는 마인드를 가지고 임하는 것이 중요한 것 같다.
- 초기에 계획을 어떻게 짜야할 지 몰라서 1주차는 A,B,C기능을 구현하고 2주차는 D,E,F를 구현하자고 정했는데 이것 보다는 1주차부터 A,B,C,D,E,F의 레이아웃을 완성시키고 기능을 하나하나 추가하는 방식이 더 괜찮을 것 같다는 생각이 들었다. 그리고 본격 프로젝트를 시작하기 전에 프론트엔드와 백엔드가 같이 어떻게 진행할 것인지 큰 지도를 그려보는 것도 프로젝트를 진행하는것에 있어 굉장한 도움이 될 것 같다.
- 다음 프로젝트에서는 더 적극적으로 소통하고 시간관리와 기록을 잘 해서 더 체계화된 프로젝트를 진행하고 싶다.
    
     
    
## 👩‍💻 앞으로 어떤 개발자가 되고 싶은지에 대한 생각

- 나는 꾸준히 기록하는것에 약한 편이다. 하지만 계속 성장하는 개발자가 되기 위해서는 기록을 꾸준히 잘 해야할 것 같다. Notion이나 Trello를 잘 활용해 기록을 잘하고 나 스스로를 객관적으로 분석하여 성장할 수 있는 개발자가 되고싶다.

## 📽 시연 영상

<iframe width="560" height="315" src="https://www.youtube.com/embed/kaVLMD1Mfi4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



## 📝 KPT

Keep : 팀의 분위기가 좋아서 재미있게 프로젝트를 진행 했다. 다음 프로젝트를 진행 할 때도 좋은 분위기를 유지할 수 있도록 노력해야겠다!

Problem : 많은 사람들이 개발을 할 땐 소통이 정말 중요하다고 강조하는데 이번 프로젝트를 하면서 정말 중요하다는 것을 느낄 수 있었다. 나는 제품상세페이지를 맡았는데 초기 미팅 때, 어떤 데이터가 들어가는지 회의를 했고 레이아웃을 진행했다. 진행하다가 BE쪽에 한번 체크 해 봤더니 새상품, 재고 등 기존 결정된 사항과 비교하면 새로 들어가는 데이터들이 있었다. 레이아웃을 다 만들고 확인 했다면 혹은 초기 미팅만 생각하고 아예 확인하지 않았다면 double job을 해야 했을 것이다. 새로운 일을 진행 할 때 마다 항상 한번 더 체크하는 습관을 길러야 겠다.

Try : 프로젝트는 2번의 sprint로 나뉘어져 있었고 각 sprint마다 정해진 ticket이 있었는데 아무래도 처음해보는 프로젝트라 어려운 점이 있었고 이 사항을 빨리 팀원들에게 공유하여 기간 내에 맡은 역할을 완성할 수 있게 하였다. 
