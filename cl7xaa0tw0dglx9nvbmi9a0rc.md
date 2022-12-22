# 2nd Team Project retrospective : DGV

# 드디어 두 번째 프로젝트!

첫 번째 프로젝트가 끝나기 무섭게 두번째 프로젝트가 시작되었다 🥹🔥 

## 🍿 팀 명 : DGV (Da Great V)
- 이번 팀 이름도 일차때와 마찬가지로 의식의 흐름을 따라갔다 😂 뭔가 CGV랑 비슷한 어감으로 하고 싶었지만 아이디어가 잘 떠오르지 않았다. 브레인 스토밍을 하며 막 던지다가 괜찮은거 발견! the great five! the의 슬랭으로 Da, 그리고 로마자 V (=five) 를 가져와서 DGV가 되었다.

## 📆 프로젝트 기간
- `2022. Aug. 29 ~ 2022. Sept. 8` (11 days)

## 👩‍💻 팀원 (총 5명)
- Front-end : 3명
- Back-end : 2명

## ⛳️ 목표
- 대한민국 영화관 웹사이트인 CGV를 모티브로 하여 SNS를 통한 로그인기능 및 마이페이지, 영화 리스트 및 상세페이지, 그리고 영화 예매기능을 구현하기

## 📝 About this Project

### ✔️ 내가 맡은 part
- 예매페이지 및 Footer 구현

### ✔️ 기억하고 싶은 code
<details>
<summary>rendering error에서 빛과 같았던 코드
</summary>
```jsx
<AreaPart>
            {locations &&
              locations.map(item => {
                return (
                  <Area
                    key={item.main}
                    onClick={() => setGetId(item.main)}
                    getId={getId === item.main}
                  >
                    {item.main}
                  </Area>
                );
              })}
          </AreaPart>
```
> locations라는 json 파일을 가져와 map을 돌려주는데 처음엔 데이터 없이 render가 되기 때문에 오류가 나고 화면 전체가 뜨지 않는 에러가 생긴다. 이때 json에서 가져온 location을 &&연산자에 걸어두어 location이 참일때, 즉 빈값이 아닐때 (빈값은 false) 실행하는 방법을 사용해 주었다. 이 방법이 여럿 map 함수들을 사용한 곳에 도움이 많이 되었다. 🥹
</details>
***

<details>
<summary>
styled-components: onClick시 변하는 style 적용한 코드!
</summary>
  ```jsx
//booking.js
  const [activeMovie, setActiveMovie] = useState('');

//movie.js
        {movies &&
          movies.map(item => (
            <List
              onClick={() => {
                setActiveMovie(item.title);
                setActivePoster(item.image);
                setGetMovieId(item.id);
              }}
              activeMovie={activeMovie === item.title}
              key={item.id}
            >
              {item.title}
            </List>
          ))}

//styled-components 💅

  ${({ activeMovie }) =>
    activeMovie &&
    `
  background-color: black;
  color: white;`}
`;
```
> 부모인 booking.js에서 activeMovie와 setActiveMovie state를 가져와서 특정 영화 제목을 클릭했을 때, 그 영화제목의 색깔과 배경이 바뀌도록 구현하였다. 즉, onClick에 setActiveMovie를 입력하여 클릭했을 때, item.title(영화제목)이 set되게 하고 set된 값이 item.title과 같으면 activeMovie가 동작하여 스타일을 바꾸는 형태로 만들었다. styled-components를 처음 사용해 보아서 처음엔 좀 헤메었고 예전에 사용하던 css와 sass가 그리웠지만 막상 적응하고 나니 별도의 파일 없이 css를 사용할 수 있어서 은근히 깔끔했고 편했다. 그리고 컴포넌트 분리를 시킬때도 컴포넌트화가 된 css를 옮겨주니 정말 편했다. 역시 인간은 적응의 동물이였다 💡
</details>
***

<details>
<summary>
애증의 달력 라이브러리 🫠
</summary>
```
function DateCom({ selectedDay, setSelectedDay, getMovieId, activeLocation }) {
  const [list, setList] = useState('');
  const today = new window.Date();
  const disabledDays = [
    {
      from: new window.Date(2022, 1, 1),
      to: today.setDate(today.getDate() - 1),
    },
  ];
  const modifiers = {
    movieDay:
      list.timeList && list.timeList.map(item => new window.Date(item.date)),
  };

  const modifiersStyles = {
    movieDay: { color: 'white', backgroundColor: 'tomato' },
  };

  useEffect(() => {
    fetch(`/data/test.json`)
      .then(response => response.json())
      .then(result => setList(result));
  }, []);

  return (
    <Date>
      <Title>날짜</Title>
      <Content>
        <CalendarWrapper>
          <DayPicker
            mode="single"
            selected={selectedDay}
            onSelect={setSelectedDay}
            locale={ko}
            onClick={() => {
              setSelectedDay(selectedDay);
            }}
            modifiers={modifiers}
            modifiersStyles={modifiersStyles}
            disabled={disabledDays}
          />
        </CalendarWrapper>
      </Content>
    </Date>
  );
}
```
> 내가 사용한 달력 라이브러리는 [📅Day-picker](https://react-day-picker.js.org/). react-calendar, date-picker를 사용해봤지만 결국 Day-picker에 정착했다. 프로젝트 초창기엔 라이브러리를 사용 가능하다고 해서 금방 할 줄 알았다. 이미 만들어진 코드를 복사 붙여넣기만 하면 된다고 생각했던것. 하지만 막상 사용해보니 직접만들고 싶어질 정도로 내가 원하는 기능대로customising는 과정이 어렵다고 느껴졌다. 초창기 계획 한 바에 따르면 달력 전체가 default로 disabled되어야 했고 영화 상영 가능한 날짜만 enabled되어야 했는데 라이브러리를 찾아보고 아무리 구글링을 해 보아도 방법을 찾을 수 가 없었다. 결국 다른 방도로 찾아낸 것이, 영화상영날짜를 색깔로 표현해서 사용자가 몇월 몇일에 특정 영화 상영이 가능한지 알 수 있게 하였다. 일단 라이브러리에 있는 disabled 기능을 살리기 위해 오늘 날짜 `new Date()`이전의 날은 모두 disable 처리를 했고 이후의 날부터 영화를 선택 할 수 있게 구현하였다. 그리고 서버에서 불러오는 날짜와 형식을 맞추기 위해 [date-fns](https://date-fns.org/)라이브러리를 추가로 사용하였고 지역과 영화이름을 클릭해서 들어오는 날짜에 스타일을 주었다.


![예매페이지.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1662953001312/8librfPb9.gif align="left")
</details>
***


### ✔️ 이 프로젝트를 통해 내가 얻은 것
- 처음 예매페이지를 담당했을 땐, 내가 과연 할 수 있을까? 라는 의심이 들었다. 거기다 익숙하지 않은 styled-components를 사용하며 더욱더 난항을 겪었고 머리속에 로직과 구조가 잡히지 않아 백엔드 측에서 원하는 데이터 달라는 대로 줄테니 말만 하라는 요청에도 응답할 수 없었다. 1차 프로젝트때는 이미 서버쪽에서 구현이 되있는 데이터를 받았고 그 상태에서 서로 조정해 나갔는데 2차 때는 어떤식으로 줘야하는지 말해달라는 요청이 들어와서 익숙하지 않았고 정확한 정보를 줘야한다는 생각에 빠르게 대응하지 못했다. 내가 정확학 정보를 줘야한다는 압박감을 느끼기 보다는 처음엔 이러한 식으로 데이터를 받으면 편할 것 같고 그 이후에 수정이 될 수 도 있다는 식으로 flexible하게 백엔드 분들에게 말해주었다면 좀 더 smooth하게 진행 되었을 것 같다. 이번 프로젝트를 하며 제일 크게 배운 점 이기도 하다.

건물 화재에 태풍까지 겪으며 멘붕인 상태가 지속되었는데 그때마다 옆에서 응원해주고 같이 해결방법을 찾으려고 노력해준 팀원들이 있어서 이겨낼 수 있었던 것 같다. step-by-step으로 하나씩 하나씩 해결해 나갔고 어느 순간 정신을 차려보니 예매페이지가 내 눈앞에 있었다. 언제 고민했냐는듯 작동하는 예매페이지를 보니 앞으로 어려움이 닥쳐와도 해낼 수 있을 것이라는 작은 희망이 생겼다 🌱

### ✔️ 시연 영상
<iframe width="560" height="315" src="https://www.youtube.com/embed/yq8nFL97u9M" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

[👉 DGV Github repository](https://github.com/Suziech/36-2nd-DGV-frontend)


## 📝 KPT
- Keep : 맡은 Ticket을 결국 수행해내는 끈기는 계속 가져갈것!

- Problem : 대화는 flexible하게! 정확하지 않더라도 try!

- Try : 재미있게 진행하고자 영화트레일러 영상도 찍고(소요시간 10분컷ㅋㅋ) 그리고 구현이 어려운 부분들은 서로 이야기하고 해결방법을 모색해 나간 점!