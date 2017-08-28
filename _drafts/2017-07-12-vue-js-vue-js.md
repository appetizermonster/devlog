---
layout: post
title: Vue.js 사용기 (Vue.js 강력 추천합니다!)
date: 2017-07-12 02:55:51 +0000
---

이번에 [Steem2KRW](https://steemit.com/kr-dev/@heejin/steem2krw-steem-krw)을 만들면서 처음 사용해본 [Vue.js](https://vuejs.org/)에 대한 얘기를 적어보려 합니다.

저는 원래 웹 개발을 전문으로 하는 개발자는 아닙니다. 지금은 게임을 만들고 있죠 :)
그래도 프로그래밍과 관련된 거의 모든 것에 관심을 가지고 있어서, 웹 프로그래밍도 꾸준히 보고 있습니다.

작년에 [Hain](https://github.com/hainproject/hain)이라는 Electron 어플리케이션을 만들었을 때, 페이스북의 [React](https://facebook.github.io/react/)를 사용했었는데요.
React를 사용하면서 굉장히 편하다는 느낌을 많이 받았습니다. 그냥 HTML과 단순 JavaScript만으로 개발하는 것과는 다른 느낌이었습니다.
좀 더 코드가 깔끔해지는 느낌을 받았습니다.

React는 Declarative Programming을 차용했습니다. 어쩌면 거꾸로 간다는 느낌도 받았죠. 왜냐하면 컨텐츠인 데이터와 코드를 합치려는 시도이기 때문입니다.
하지만 이 패러다임으로 인해서 웹 프로그래밍이 굉장히 쉽고 편리해졌다고 생각됩니다. 데이터의 흐름에 대해서 신경 쓰지 않고, 화면이 어떻게 구성되는지만 생각하면 되니까요.

그래서 Steem2KRW를 만들기 시작할 때 처음에는 React를 사용하려 했습니다.
그런데... 너무 오랜만에 웹 프로그래밍을 하는데 React의 경우 세팅해야할 부분이 너무 많습니다.
물론 최근의 웹 프레임워크들은 거의 모두 다 너무 많은 세팅을 요구합니다. 심지어 프론트엔드 프로그래밍하는데 Node.js를 설치해야하고, Webpack이니 Babel이니, 세팅해야할 것들이 너무 많습니다.

저는 단지 굉장히 짧은 시간동안 핵심만 빠르게 만들어보고 싶었는데, React를 사용하려니 배보다 배꼽이 더 커지는 느낌이 들었습니다.
그렇다고 그냥 JavaScript로 만들기에는 노가다가 많이 있을 것 같아고요.

그래서 찾은 대안이 [Vue.js](https://vuejs.org/)입니다.

<center><img src="https://steemitimages.com/DQme2qEryatvdZyjrbsbJkj5C5imDaSxaHzV27NQM36Rj26/image.png" style="max-width:100%;"></center>

Vue.js를 만나고 나서 새로운 세계를 경험했습니다.

제가 Steem2KRW에서 원했던 건 HTML 컴포넌트에 대한 단순 데이터 바인딩이었습니다.
HTML 컴포넌트와 그 데이터를 JavaScript에서 손쉽게 조작하고 싶었죠.

아마 React를 사용했으면 아래 그림의 코드처럼 모든 것을 JavaScript로 만들었을 겁니다.
<center><img src="https://steemitimages.com/DQmVEwjq8BrVTQLee22jBadswVg23HLSkXrf2Tn9U6KixKE/image.png" style="max-width:100%;">
_Hain의 코드 일부_</center>

하지만 Vue.js를 사용하면 아래처럼 HTML에 직접 뷰와 관련된 로직을 넣고, JavaScript에는 데이터만 넣어주면 됩니다.
그리고 JavaScript로 데이터를 바꿔주면 뷰는 자동으로 바뀌는 거죠.

<center><img src="https://steemitimages.com/DQmSzSM61Tcs7tRQjqDsnWg8XqnmFwo8wumNHEDZZSUDYih/image.png" style="max-width:100%;">
_뷰를 담당하는 HTML 코드_</center>

<center><img src="https://steemitimages.com/DQmeQVMm2Drf2dJdB7FYKFcsNs2A5WvL9cD2ToHE4Ms1Qre/image.png" style="max-width:100%;">
_데이터를 담당하는 JavaScript 코드_</center>

React에서 [JSX](https://facebook.github.io/react/docs/introducing-jsx.html)라는 특별한 Template 언어를 사용해서 JavaScript와 HTML을 통합시켰다면, Vue.js는 그냥 HTML을 사용하는 것 같은 느낌입니다.
그래서 더 단순하고, 쉽습니다. JSX를 쓰기 위해서 Babel을 세팅할 필요도 없고요.

아직 Vue.js의 다른 부분에 대해서는 많이 탐구해보지 못했습니다. 딱 필요한 만큼만 빠르게 학습해서 썼으니까요.
하지만 사용법을 익히고, 세팅하는데 10분도 안걸린 것 같습니다.

작은 사이즈의 웹 어플리케이션을 빠르게 만들어보고 싶으신 분들은 [Vue.js](https://vuejs.org/)를 한번 사용해보세요. 강력 추천합니다 👍
단순 HTML+JavaScript보다 빠르고 직관적이게 웹 어플리케이션을 만들 수 있고,
이미 너무 복잡해진 React처럼 세팅이 필요하지도 않습니다.

저도 계속 Vue.js를 많이 써보면서 공부해야겠습니다.
감사합니다.