# How to change the format of dates?

2차프로젝트를 진행하면서 내가 과연 할 수 있을까? 라고 생각한 부분을 구현했고 기뻐서 블로그를 쓰게 되었다 🤓

아래의 그림처럼 달력의 특정 날짜를 클릭했을 때, 하단 바에 내가 선택한 날짜가 나타나게 하는게 나의 목표!
달력 라이브러리도 아직 익숙하지 않은데 (👉[블로그보러가기](https://suzie.hashnode.dev/a-nice-calendar-library-for-react)) 내가 선택한 날짜를 특정 포멧으로 + 한국어 요일이 나타나게 해야했다.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662263779510/dDcQ88Wni.png align="left")

> 출처 : CGV website

일단 daypick library에서 보였던 정체불명의 이 분, `
import { format } from 'date-fns';`

format이라.. 아주 suspicious 하여 바로 조사 착수 🤔

구글링 해보니,

👉 [date fns](https://date-fns.org/) - 공식문서
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662264367889/8ZtJPNDdU.png align="left")

자바스크립트의 dates들을 manipulating 할 수 있다고 한다! 
공식문서를 보며 이것 저것 실험해 보았고 `import ko from 'date-fns/locale/ko';`를 임포트 해주면 한국어로도 표현이 가능한 부분!

```
import { format } from 'date-fns';
import ko from 'date-fns/locale/ko';

                  <Location>
                    일시&nbsp;
                    {selectedDay &&
                      format(selectedDay, 'PP (eee)', { locale: ko })}
                    &nbsp; {activeTime}
                  </Location>
```

'PP' -> 날짜 표현 format (2022.09.04)

eee -> 요일 표현 format (일)

{locate:ko} -> 한국어로 날짜, 요일 표시

내가 작업중인 컴포넌트에 적용시켜보았다.


![format.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1662264901274/WbJv4CMBj.gif align="left")

아주 잘 작동하는 것을 볼 수 있다. 🥹

다음주 목요일까지 2차 sprint 달려 달려~! 🏃‍♀️🏃‍♀️🏃‍♂️🏃‍♂️🏃‍♂️

  const data = selectedDay.toLocaleString('sv');
  console.log(data);

이건 new date 날짜 포멧을 바꿔줌 