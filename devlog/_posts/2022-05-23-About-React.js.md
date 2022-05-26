---
layout: post
title: About React.js
image: 
  path: /assets/img/blog/jeremy-bishop@0,5x.jpg
description: >
  본격적인 React.js 공부를 하기전 간단하게 리액트가 무엇인지 짚고 넘어가려합니다.
sitemap: false
---
<style>
.p {
  font: italic serif;
  color: gray;
}
</style>

<strong>Hello React!</strong><br>
스크립트 라이브러리의 하나로서 사용자 인터페이스를 만들기 위해 사용된다.<br> 
페이스북과 개별 개발자 및 기업들 공동체에 의해 유지보수된다.<br>
리액트는 싱글 페이지 애플리케이션이나 모바일 애플리케이션 개발에 사용될 수 있다.
<div class="p">(reference: 위키백과)</div>
{:.lead}


- Table of Contents
{:toc .large-only}

## Need for React?
 - html과 css, javascript를 이용해서 웹 페이지를 만들 수 있지만, react를 이용해 사용자와 상호작용할 수 있는 동적인 UI를 쉽게 만들 수 있기 때문에 많이 이용한다.

## What is React?
- ui기능만 제공한다. 전역 상태 관리, 라우팅 또는 빌드시스템등은 개발자가 직접 구축해야함<br>
  ✔높은자유도, 번거로움 <br>
  ✔creat-react-app 으로 다소 해소 가능
<br><br>
- 자동으로 업데이트 되는 UI
<br><br>
- 리액트를 사용하지않으면 브라우저의 dom을 직접 수정해야함

<h2 class="h3 hr-bottom"></h2>

- render함수는 순수 함수로 작성<br>
  ✔랜덤 함수 사용하거나 외부 상태를 변경하면 안된다.
  <div class="p">(순수함수: 부수효과가 없는 함수 즉, 어떤 함수에 동일한 인자를 주었을 때 항상 같은 값을 리턴하는 함수)</div>
<br>
- state는 불변 변수로 관리<br>
  ✔객체의 속성을 변경 할 때 새로운 객체를 만들어서 값을 하당
<br><br>
👉순수함수와 불변변수를 적극 활용하면 복잡도가 낮아지고 버그 확률이 줄어듦.

<h2 class="h3 hr-bottom"></h2>

- 가상돔을 통해서 ui를 빠르게 업데이트<br>
  ✔불필요한 ui업데이트가 줄어들어 성능이 좋아짐<br>
  ✔가상돔 때문에 순수 자바스크립트보다 무조건 빠르게 동작한다는것은 아니다. 
   프로젝트 성격에 따라 성능 최적화 방법은 다를 수 있음

<br>

## Characteristics of React
- <strong>단방향 데이터 흐름</strong><br>
복잡한 앱에서도 데이터 흐름에서 일어나는 변화를 보다 예측 가능하다.

<br>

- <strong>Component 기반 구조</strong>
 > Component는 독립적인 단위의 소포트 모듈이다.

 &nbsp; React는 UI를 여러 컴포넌트를 쪼개서 만든다.<br>
 한 페이지 내에서도 여러 각 부분을 독립된 컴포넌트로 만들고, 이 컴포넌트를 조립해 화면을 구성한다.<br>
컴포넌트 단위로 쪼개져 있기 때문에, 코드를 파악하기 쉬우며 재사용성이 높다.<br> 
 &nbsp; 코드를 반복해 입력 할 필요 없이 컴포넌트만 import해 사용해면 되기에 간편하며, 애플리케이션이 복잡해지더라도 코드의 유지보수가 용이 해진다.

<br>

 - <strong>Virtual DOM</strong>
 > DOM은 html, xml, css 등을 투리 구조로 인식하고, 데이터를 객체로 간주하고 관리하며 리액트는 이 DOM트리 구조와 같은 구조체를 Virtual DOM으로 가지고 있다.

 &nbsp; 이벤트가 발생할 때 마다 Virtual DOM을 만들고, 다시 그릴 때 마다 실제 돔과 비교해 변경이 필요한 최소한의 변경 사항만 realDOM에 반영해, 앱의 효율성과 속도를 개선할 수 있다. 

<br>

- <strong>Props & State</strong>

👉Props<br>
&nbsp; Props란 부모 컴포넌트에서 자식 컴포넌트로 전달해 주는 데이터를 말한다.<br>자식 컴포넌트에서 전달받은 props는 변경이 불가하고 props를 전달해준 최상위 부모 커뫂넌트에서만 변경 가능 <font color="gray" style="italic">읽기 전용이라 생각하면 쉽다.</font>
<br>

👉State<br>
&nbsp; State는 컴포넌트 내부에서 선언하며 내부에서 값을 변경할 수 있다.<br> State는 동적인 데이터를 다룰 때, 사용자와의 상호작용을 통해 데이터를 동적으로 변경할 때 사용한다.<br> 
&nbsp; 클래스형 컴포넌트에서만 사용할 수 있고, 각각의 State는 독립적이다.

<br>

- <strong>JSX</strong>

&nbsp; JavaScript를 확장한 문법이다.
리액트에서 JSX사용이 필수는 아니지만 권장하고 있다.<br>
 > 모든 것을 설명하기엔 어렵다. 아래 공식 문서를 확인하는 것을 추천한다.<br><a href="https://ko.reactjs.org/docs/introducing-jsx.html">React의 JSX</a>
<!-- Ever since the introduction of Dark Mode, link styles have been a bit of an issue. Specifically, finding an accent color that worked on both light and dark backgrounds was the problem. With Hydejack 9, the [link style](#linking-in-style) has been revamped so that legibility is no longer tied to the choice of accent_color, giving you much more freedom in creating a unique design flavor for your site. -->


<!-- [^1]: If you are a fan of the old two-column layout, or don't like modern design tropes such as mega headlines, Hydejack lets you revert these changes on a case-by-case basis via configuration options.

[^2]:
      Search was mainly tested for English and German. Please let me know about issues in other languages. 
      While I've tried to find a multi-language solution, most showed drastically worse  results for the English base case.
      If you're technically inclined, you can adopt the code located in `_includes/js/search-worker.js` to your needs.

 -->
