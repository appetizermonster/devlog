---
layout: post
title: React Native - Flex 레이아웃 이해하기
---

최근 간단한 앱을 만들어보기 위해서 **React Native**를 공부해보고 있습니다. 그러다가 React Native의 레이아웃 시스템인 **Flex Layout**에 대해서 제 자신이 좀 더 깊게 이해하기 위해서 공부가 필요하다는 생각이 들었습니다.

# React Native?

React Native는 기본적으로 웹 기술(HTML, CSS, JavaScript)을 이용해서 앱을 만들기 위한 도구입니다. 한 때 웹 기술을 이용해서 앱을 만드는 방법 중에 하나인 Hybrid App이 유행했고, React를 만든 Facebook도 페이스북 앱을 Hybrid App으로 만들기도 했죠. 하지만 모바일 디바이스가 충분히 빨라진 지금도 웹 기술을 그대로 이용해서 사용자들의 기대에 부흥할 정도로 빠르게 동작하는 앱을 만들기는 굉장히 어렵습니다. 그리고 Hybrid App은 실패했습니다.

# Flexbox

React Native의 Flex Layout은 CSS의 Flexbox를 거의 그대로 구현했습니다.
