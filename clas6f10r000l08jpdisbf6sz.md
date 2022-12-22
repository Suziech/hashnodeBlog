# [HomeBrew] how to install Homebrew on Mac (M1)

기업 과제를 위해서 `Homebrew`를 설치해야 했는데 homebrew 공식홈페이지에 나온 대로 아래와 같이 설치해도 계속 `zsh: command not found: brew`라는 error가 떴다. 설치했는데 왜 안되지?!!?!? 🤯

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

구글에 검색해보니 설치 후 아래의 코드를 추가로 더 입력해 주면 가능하다고 한다.

```
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```
오예!! 성공! 👍 [출처 : stackOverFlow](https://apple.stackexchange.com/questions/148901/why-does-my-brew-installation-not-work)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669119033202/pTTOC_BgI.png align="left")
