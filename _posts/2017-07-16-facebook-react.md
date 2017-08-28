---
layout: post
title: Facebook의 React를 사용할 때 주의해야 할 라이센스 문제
date: 2017-07-16 11:38:09 +0000
---

<center><img src="https://steemitimages.com/DQmRQfCMx9feJZstXZCPDndqFWsaApsdduQ3HmT3JftF5ff/image.png" style="max-width:100%;">
</center>
Facebook의 [React](https://facebook.github.io/react/)는 웹 프로그래머라면 누구든 사용해본 경험이 있을 정도로 대세인 오픈 소스 프로젝트인데요. (지금 여러분이 사용하고 계시는 스팀잇 웹사이트도 React를 사용해서 만들었죠.)

저도 React를 사용해본 적이 있지만, 라이센스에 대해서는 크게 신경쓰지 않았습니다.
상용 프로그램에도 React 코드를 사용할 수 있게 허가해주는 BSD 라이센스를 적용하고 있고, 거기에 추가로 조건 없이 특허에 대한 허가를 내주는 것으로 알고 있었거든요.

그러다가 오늘 [Hacker News](https://news.ycombinator.com/)에서 [아파치 재단이 페이스북에서 사용하고 있는 오픈소스 라이센스인 "BSD+Patent" 라이센스를 적용한 코드를사용하는 것을 금지했다](https://news.ycombinator.com/item?id=14779881)는 포스트를 봤습니다.
아파치 재단의 프로젝트에는 React를 사용할 수 없다는 얘기입니다.

문제가 되는 점은 React가 사용하고 있는 "BSD+Patent"에서 명시한 특허 사용에 대한 조건입니다.
아래는 특허 사용 허가서 중 일부입니다.
```
The license granted hereunder will terminate, automatically and without notice,
if you (or any of your subsidiaries, corporate affiliates or agents) initiate
directly or indirectly, or take a direct financial interest in, any Patent
Assertion: (i) against Facebook or any of its subsidiaries or corporate
affiliates
```
---
사용자가 페이스북에 대해서 어떠한 특허 소송이라도 제기하는 경우 자동으로 React에 대한 특허 사용권한을 잃게 됩니다.
React와 관련되지 않은 특허 소송이라도 상관 없습니다.

예를 들면, **A**라는 회사가 페이스북의 React를 사용하고 있는데, 페이스북이 **A** 회사의 특허를 침해하여 **A**가 페이스북에 특허 소송을 제기하는 경우 **A**는 React 사용 권한을 잃게 됩니다. 그리고 React가 **A**사의 핵심 제품에 탑재되어 있는 경우 문제가 커질 수 있습니다.
(물론 실제로 어떤 결과가 있을지는 법원의 결정에 따라 달라질 수 있습니다)

그리고 현재 React 레포지터리에 [라이센스 변경을 요청하는 이슈](https://github.com/facebook/react/issues/10191)가 등록되어 토론이 진행되는 것 같습니다. 이에 따라 더 유연한 라이센스로 변경될지도 모르겠습니다.

React를 사용하시는 분들(특히 상업용으로 사용하시는 경우)은 라이센스에 대해서 자세하게 알아보고 사용하시는게 좋을 것 같습니다.
감사합니다.