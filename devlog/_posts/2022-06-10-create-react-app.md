---
layout: post
title: create-react-app
image: 
  path: /assets/img/blog/jeremy-bishop@0,5x.jpg
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

## create-react-app을 이용해 구축해보기

<br>

&nbsp;cra_test라는 이름으로 프로젝트를 구축해보겠습니다. 터미널에 아래와 같은 명령어로 구축하겠습니다.
<code>npx create-react-app cra_test</code>

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

오늘은 너무 피곤해서...디버깅만 하고 잠들어 버렸습니다. 내일 추가할게용