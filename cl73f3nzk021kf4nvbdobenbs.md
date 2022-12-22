# [1st project] TabomGalagsin #03

# 3rd day of the project!

상단 메뉴버튼을 hover했을 때 dropdown 기능을 다 구현했다고 생각했지만 사실 살짝 오류가 있었다. 마우스가 메뉴버튼을 hove하지 않으면, 그러니까 메뉴버튼을 벗어난 nav bar로 마우스를 옮기면 dropdown메뉴가 보이지 않아야하지만 메뉴버튼에서 마우스를 내려 바로 dropdown메뉴로 이동하면 dropdown메뉴가 사라지지않고 그대로 유지되어야 하는데, 내가 구현했던걸 다시 살펴보니 마우스가 메뉴버튼을 hover하고나서 다시 그 dropdown 메뉴를 종료시켜주려면 다시 한번 hover을 해주어야 작동이 되었다. 

이 오류를 해결하려면

1. state는 default가 false, 하지만 마우스로 hover해주면 true로 벗어나면 false로 상태변화가 일어나야 한다. 
2. 마우스가 dropdown 아래로 움직이면 true상태가 유지되어야 한다.

true상태를 유지하기 위해 dropdown을 메뉴버튼을 감싸는 `<div>` 의 하위level로 넣어주었다. 그리고 이 두개의 (메뉴버튼, dropdown)을 감싸는 div에 onMouseEnter addEventListener를 추가하여 마우스가 dropdown메뉴로 이동해도 true를 유지하여 메뉴가 사라지지 않게 그리고 마우스가 dropdown이 아닌 다른곳으로 가면 상태가 false화 되며 dropdown메뉴가 사라지는거 구현 성공! 


```jsx
<div className={`navBottomContainer ${color}`}>
        <div
          onMouseEnter={() => setIsMouseEnter(!isMouseEnter)}
          onMouseLeave={() => setIsMouseEnter(!isMouseEnter)}
        >
          <i className="fa-solid fa-bars navIcon menu" />
          {isMouseEnter && <Dropdown />} 
        </div>

{/* <div on(EventListener)>
        <button>on(EventListener)</button>
        {true && <Component />}
      </div> */}
```

하지만 성공했다는 기쁨도 잠시… 나에겐 무시무시한 `carousel`이 기다리고 있었는데….(to be continued)