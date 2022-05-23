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

<!-- Ever since the introduction of Dark Mode, link styles have been a bit of an issue. Specifically, finding an accent color that worked on both light and dark backgrounds was the problem. With Hydejack 9, the [link style](#linking-in-style) has been revamped so that legibility is no longer tied to the choice of accent_color, giving you much more freedom in creating a unique design flavor for your site. -->


<!-- [^1]: If you are a fan of the old two-column layout, or don't like modern design tropes such as mega headlines, Hydejack lets you revert these changes on a case-by-case basis via configuration options.

[^2]:
      Search was mainly tested for English and German. Please let me know about issues in other languages. 
      While I've tried to find a multi-language solution, most showed drastically worse  results for the English base case.
      If you're technically inclined, you can adopt the code located in `_includes/js/search-worker.js` to your needs.

 -->
