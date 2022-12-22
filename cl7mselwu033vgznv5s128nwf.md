# A nice Calendar Library for React

최근 2차 프로젝트를 진행하면서 CGV website를 클론중이다. 내가 맡은 파트는 예약페이지라서 달력이 필수적으로 필요했다. 구글링을 해가며 여러 달력 라이브러리를 탐색했고 총 3가지를 써보게 되었다.

첫 번째로 시도 했던 calendar library는 `datepicker`였는데 처음에 빈 inpu창이 나오고 이걸 클릭 해야 사용할 수 있는 기능이였다. 하지만 내가 원했던 기능은 달력이 그대로 보여지는 것 이였고 목적과 맞지 않아 삭제했다. 

두 번째로 시도했던 library는 `react-calendar`였다. 하지만 정보가 많이 없고 사용하기 복잡했다.

세 번째로 mentor님께서 추천해주신 `day-picker`을 사용해 봤는데 공식문서가 아주 자세하게 예시와 함께 작성되어 있으며 커스터마이징을 하기 정말 좋은 기능들이 많았다. 

> `Day-Picker` https://react-day-picker.js.org/


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662262624339/7w5SCsnW_.png align="left")

> 내가 지금 진행하고 있는 예약페이지에 라이브러리를 추가하여 다른 component와 같은 스타일로 커스터마이징해주었다.

Recently I'm in my 2nd project of cloning a website and since my part is making a booking page, I had to find a library to add a calendar in. I've tried 3 libraries and I got to stick to the one library.

To get straight to the point, I strongly recommend to use `Day Picker` https://react-day-picker.js.org/

it has a good website that explains how to use this library with many examples.

Since I was cloning the Korean website, I wanted to have a calendar with a korean language. also I wanted to have the day picker colour as black. 

for both functions, I was able to make it with this library.