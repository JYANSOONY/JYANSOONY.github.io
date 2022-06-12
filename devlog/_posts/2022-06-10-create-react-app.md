---
layout: post
title: create-react-app
image: 
  path: /assets/img/blog/npmHMR.png
description: >
  create-react-app은 리액트 개발환경을 구축해주는 도구입니다. create-react-app으로 리액트 시작하기 해볼게요
sitemap: false
---
<style>
.img{
  text-align : center;
}
span {
  font-style: italic serif;
  color: gray;
}
</style>

- Table of Contents
{:toc .large-only}

## create-react-app ?

<br>

리액트 개발 환경을 직접 구축하려면 많은 지식과 노력이 필요합니다. 빌드 시스템 구축을 위해 웹팩이나 바벨을 사용하거나 테스트 환경 구축을 위한 jest 테스트 프레임워크를 사용해야합니다.<span>그 외 eslint, polyfill, HMR, CSS 후처리 등등...</span>

👉위와 같은 번거로운 것들을 create-react-app이 자동으로 구축해서 제공을 해줍니다. wow~

<br>

## create-react-app을 이용해 프로젝트 구축해보기

<br>

&nbsp;cra_test라는 이름으로 프로젝트를 구축해보겠습니다. 터미널에 아래와 같은 명령어로 구축하겠습니다.
<code>npx create-react-app cra_test</code>

 >프로젝트를 구축 할 때 지금과 같이 create-react-app 으로 하나 Next.js프레임워크를 쓰나 고민할 수 있는데, 이 둘의 큰 차이점은 '서버사이드 렌더링' 지원이라고 볼 수 있습니다. 서버사이드 렌더링이 필수적인 프로젝트라면 Next.js를 선택하는 것이 좋습니다.

🧨<br>
&nbsp;하지만 오늘도 순탄치 않게 프로젝트 생성 때부터 노드 버전 문제로 error를 마주하게 됩니다. 맥이라면 <code>n lts</code>로 손쉽게 버전을 업데이트 할 수 있지만 윈도우는 지원하질 않습니다 이런!

<br>
&nbsp;<a href="https://github.com/coreybutler/nvm-windows/releases">nvm.exe</a> 에서 설치파일을 다운 받은 후,
cmd<span>(관리자 모드)</span>창 혹은 터미널 powershell에서 아래와 같이 작업하면 된다. <span>필자는 터미널에서는 nvm인식이 안돼 cmd를 관리자 모드로 열어두고 작업했다.</span>
<br>
<code><br>
node -v <br>
nvm list available //버전 리스트 확인<br>
nvm install 18.2.0 //nvm install 원하는 버전 선택 <br>
nvm list //설치된 버전들 리스트 확인<br>
nvm use 18.2.0<br>
node -v //버전 잘 적용 됐는지 확인
</code>

<br>

<div class="img">
<img src="/assets/img/blog/create_cra.png" alt="create_cra">
</div>

<h2 class="h3 hr-bottom"></h2>

&nbsp;설치가 끝난 후에 <code>npm start</code>로 구동시키고 프로젝트를 수정하면, 수정하는 즉시 반영이 됩니다.
<br>
<div class="img">
<img src="/assets/img/blog/npmHMR.png" alt="npmHMR">
</div>
<br>
&nbsp;위 사진은 서버를 내렸다 올리거나 새로고침을 해서 반영된 것이 아니라 실시간으로 적용이된 화면입니다. HMR 기능 덕분이죠.<br>&nbsp;이렇게 HMR이 동작하는것은 npm start로 프로젝트를 시작했을 때 로컬에 서버를 띄워서 브라우저와 통신을 하기 때문에 가능한 것입니다. <span>개발 모드이기 때문에 배포할 때는 npm start사용하시면 안됩니다...</span>

<br>

## 프로젝트 둘러보기
<br>

~~~js
// File: "index.js"

  import logo from './logo.svg';
  import './App.css';

  function App() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <p>
            Hello World! I am JYANSOONY.
          </p>
          <a
            className="App-link"
            href="https://reactjs.org"
            target="_blank"
            rel="noopener noreferrer"
          >
            Learn React
          </a>
        </header>
      </div>
    );
  }

  export default App;
~~~

&nbsp;이런식으로 css나 이미지 파일도 자바스크립트에서 import해서 사용하고 있는데 이렇게 사용하면 이미지 경로에 해시 값이 들어가기 때문에 브라우저 캐싱을 효율적으로 활용할 수 있습니다.
 &nbsp;또한 데이터 사이즈가 크거나 항상 필요한게 아닐 때, 필요한 상황에만 데이터를 받아오는게 좋겠죠?
<br>이미지 뿐만 아니라 데이터를 다룰 땐 json 파일도 import해 사용할 수 있습니다.
<br>
&nbsp;또한 데이터 사이즈가 크거나 항상 필요한게 아닐 때, 필요한 상황에만 데이터를 받아오는게 좋겠죠?

~~~js
// File: "data.json"
 
 {
    "name" : "JYANSOONY",
    "age" : 25
 }
~~~

 ~~~js
// File: "index.js"

import logo from './logo.svg';
import './App.css';

function App() {
  function onClick(){ //import예제 추가
    console.log({data});
  }
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        {/* import예제 추가 */}
        <button onClick={onClick}>데이터 보여지기</button>
        <p>
          Hello World! I am JYANSOONY.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
 ~~~

 &nbsp;만약 이렇게 버튼을 클릭했을 때만 보여주는 상황이라고 할 떄 별다른 처리가 없었다면, 클릭 하기도 전에 data가 포함이 된채로 번들 파일이 구성이 됩니다.
 동적으로 받아오려면

 ~~~js
 // File: "index.js"

  function onClick(){ //import예제 추가
      import('./data.json').then(({default : data}) => {
        console.log({data});
      })
    }   
 ~~~

 &nbsp;이렇게 수정만 해주면 동적으로 데이터를 받아올 수 있습니다.

