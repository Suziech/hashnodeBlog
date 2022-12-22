# [Vue] Installation Error in Mac

Vue 설치할 때 Mac의 경우 아래와 같은 오류를 마주칠 수 있다.


![Screenshot 2022-09-14 at 3.31.49 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1663138182037/6B1oFbQgB.png align="left")

ERR 메세지를 읽어보면 permission에 관련된 문제이다.
이럴 경우 sudo 를 앞에 붙여 강제로 설치하면 설치가 됨!

```
sudo npm install -g @vue/cli
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1663138151047/Yf7xAegKz.png align="left")
