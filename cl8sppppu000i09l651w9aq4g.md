# [React] CSR / SSR with Next.js

# CSR(Client-side Rendering) 이란?
- CSR은 HTML node를 구축하기 위해 HTML DOM을 조작하는 브라우저 내에서 Javascript 코드를 실행함으로써 browser에서 HTML components 를 생성하는 것을 의미합니다.

# CSR 장점
- 초기 load 후 웹 사이트의 모든 HTML이 client 측에서 생성되므로(Javascript에 의해), HTML을 얻기 위한 server로의 왕복 없어 아주 빠르고 responsive합니다. 
또한 실시간 데이터 fetch가 외부 API calls를 client-side의 javascript 코드가 만듦으로서 client-side에서 처리 가능합니다. 

# CSR 단점

- **긴 초기 load time** : Javascript가 다 다운로드 될 때까지 기다려야함
- **SEO 및 page ranking에 부정적인 영향** : CSR 웹 페이지는 대부분 비어 있고 HTML을 생성하는 JS 코드에 대한 링크만 있기 때문에 웹 크롤러는 이들을 빈 페이지로 볼 수 있다.
- **Javascript가 disabled되면 User는 빈 화면을 보게 됨** : User가 JavaScript를 자신의 browser에서 disabled해놓은 상태라면 HTML이 생성되지 못할 것이다.

# SPA(Single Page Application)로 구성된 웹 앱에서 SSR(Server-side Rendering)이 필요한 이유

- CSR의 단점을 보완하기 위해 필요하다. 특히 SPA의 html은 `<div id="root"> </div>` 이런 구조이기 때문에 SEO에 상당히 부정적인 영향을 끼친다. 하지만 그렇다고 해서 SSR만 써야하는건 아니다. 보안에 관련해서는 검색창에 뜨지 않는게 보안상 좋기 때문에 적절히 사용해야한다.

### Next.js 프로젝트를 세팅한 뒤 yarn start 스크립트를 실행했을 때 실행되는 코드를 nextjs github 레포지토리에서 찾은 뒤, 해당 파일에 대한 간단한 설명을 첨부해주세요. 
- 이게 뭔말이지? 🤷‍♀️ 과제 자체를 이해할 수 없다 Next.js 프로젝트 세팅 했고, yarn start 스크립트 실행 했다.

![Screenshot 2022-10-05 at 9.45.33 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664930772621/BcqEtKfr0.png align="left")
> `yarn start`를 실행 한 화면

이걸 실행 했을 때 실행되는 코드? 이걸 github repository에서 찾아라?


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664930900358/E8ZOx8aKq.png align="left")
> 여기서 yarn start실행 후 실행되는 코드를 찾으라고? 어떻게 찾지..?


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664930977452/vbjxgjOCg.png align="left")
> 일단 yarn을 검색해보니 파일들이 나온다. 이걸 체크하라는건가? 근데 yarn start를 실행하고 나오는건지 아닌지 어떻게 알지?

> yarn start와 nextjs의 상관관계가 뭐길래 yarn start를 실행했을 때 실행되는 코드를 찾으라고 하는걸까? yarn을 사용하지 않고 npm으로 nextjs를 사용하는것도 가능할텐데.. 

일단 yarn이 뭐지?
- Yarn is a package manager that doubles down as project manager. Whether you work on one-shot projects or large monorepos, as a hobbyist or an enterprise user, we've got you covered.
- yarn npm은 package manager로 서로 비슷한데 ... next js에서 yarn start를 했을 때 npm start와 다른점이 있는건가..?

- 점점 미궁속으로 빠진다... nextjs챌린지가 끝나면 깨달을것인가..?!

[Next.js 세팅 가이드](https://nextjs.org/docs)
[Next.js Github 레포지토리](https://github.com/vercel/next.js/)
