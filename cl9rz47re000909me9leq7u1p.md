# [JavaScript] 실행 컨텍스트 (execution context)

# 큐(Queue)와 스택(Stack)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666881386372/Z7jCMcd6Z.png align="left")

- **스택(Stack)** : 출입구가 하나인 깊은 우물같은 데이터 구조 (순서대로 `a, b, c d`를 저장했으면 `d,c,b,a`순으로만 꺼낼 수 있다.) 스택이 넘처나면 에러가 발생함.

ex) 웹사이트에서 뒤로가기를 눌렀을 때, `ctrl-z`을 눌렀을 때

- **큐(Queue)** : 양쪽이 모두 열려있는 파이프같은 데이터 구조. 보통 한쪽은 입력, 다른 한쪽은 출력만을 담당 (순서대로 `a,b,c,d`를 저장했으면 먼저 들어간 `a,b,c,d` 순으로 꺼낼 수 있다)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666929609897/YGsQDJq68.png align="left")

> 1. 스택은 최상단을 먼저 처리하므로 console.log(1)을 실행한다.
> 2. setTimeout은 오래걸리기 때문에 stack에서 알아서 대기실로 보낸다.
> 3. 밑에 있던 console.log(3)을 실행한다.
> 4. 대기실로 갔던 setTimeout함수는 queue로 들어가고 stack에 아무것도 없는게 확인 되면 stack으로 들어가 console.log(2)가 실행된다.

>> **여기서 생긴 궁금한 점!!** 만약 1초 후, 2초 후, 3초후 실행하는 setTimeout이 여러개이고 순서가 3초가 가장 먼저 그다음 2초 1초라면 대기실에서 실행되는 시간을 기준으로 queue로 보내는건가?! 🤔

# 실행 컨텍스트(execution context)란?

> - 실행할 코드에 제공할 환경 정보들은 모아놓은 **객체**

> - 자동생성되는 전역공간 및 eval()을 제외하고 실행 컨텍스트를 구성하는 방법은 **함수를 실행**하는 것

> - 실행 컨텍스트가 콜스택의 맨 위에 쌓이는 순간이 곧 현재 실행할 코드에 관여하게 되는 시점

> - 어떤 실행 컨텍스트가 활성화될 때 자바스크립트 엔진은 해당 컨텍스트에 관련된 코드들을 실행 하는데 필요한 환경 정보들을 수집해서 실행 컨텍스트 객체에 저장

>> **실행 컨텍스트 객체에 저장되는 내용들**

>> **VariableEnvironment **: 현재 컨텍스트 내의 식별자들에 대한 정보 + 외부 환경 정보, 선언 시점의 LexicalEnvironment의 스냅샷으로, 변경사항은 반영되지 않음

>> **LexicalEnvironment** : 처음에는 VariableEnvironment와 같지만 변경사항이 실시간으로 반영됨

>> **ThisBinding** : this 식별자가 바라봐야 할 대상 객체




![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666927061222/D_hjTfYNi.png align="left")
