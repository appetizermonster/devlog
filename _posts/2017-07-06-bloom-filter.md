---
layout: post
title: 알아두면 좋은 자료 구조, Bloom Filter
date: 2017-07-06 03:31:45 +0000
---

확률형 자료 구조, **Bloom Filter**에 대해서 들어보신 적 있으신가요?
저는 처음 들었을 때 게임 등에서 사용하는 Bloom Effect를 얘기하는 줄 알았어요.
하지만 아니더군요😳

<center>
<img src="https://steemitimages.com/DQmXdLDBN8QqjsWEnAATcNSdWDvG4Md3FuE7ZZCRsZBTJDB/image.png" style="max-width:100%;">
Bloom Effect를 적용한 게임 화면
</center>

# Bloom Filter?
Bloom Filter는 특정 원소가 집합에 속하는지 검사하는데 사용할 수 있는 **확률형 자료 구조**입니다.
굉장히 빠르고, 메모리 효율적이라는 장점이 있습니다.
하지만! **확률형 자료 구조**이기 때문에 이 친구가 가끔 틀린 사실을 뱉어낼 수도 있습니다.

다행인 점은 이 친구가 **집합에 속한 원소를 속하지 않았다고 말하는 일(False Negative)은 절대 없다**는 것입니다.
반대로 **속하지 않은 원소를 가끔 속해있다(False Positive)**고 얘기하기는 하죠.

예를 들어서 `('aa', 'bb', 'cc', 'dd')`라는 집합을 Bloom Filter를 이용해 저장하면 이 안에 `'xx'`라는 원소가 있는지 검사했을 때 있다고 얘기할 수도 있다는거죠.
하지만 `'aa'`라는 원소가 있는지 검사했을 때 없다고 나올 일은 절대 없다는 것입니다.

## Bloom Filter의 원리
<center>
<img src="https://steemitimages.com/DQmXogWxu9E5FUM6FY1Rn7tj7YyM7NDnxN5Hiyig87jEjr9/image.png" style="max-width:100%;">
</center>
Bloom Filter의 원리는 비교적 간단합니다. 해싱 함수를 이용해서 원소를 해싱한 다음, 위 그림처럼 모두 더하는 겁니다.
그리고 원소의 존재 여부를 검사할 때는 검사 대상 원소를 해싱한 다음 Bloom Filter에 계산된 해시가 마스킹되어 있는지 확인하는 것이죠.

# 그럼 어디에 쓰는거지?
집합의 크기가 굉장히 크거나 집합의 속해있는 원소의 크기가 커서 원소가 집합에 속해있는지 정확히 판단하는데 시간이 오래걸리는 경우
이 과정의 전처리 과정으로 Bloom Filter를 이용해서 아예 집합에 속할 일이 없는 원소를 미리 걸러낼 수 있습니다.

**Google Chrome은 위험한 사이트 검사에 Bloom Filter를 사용**한다고 알려져 있습니다. Bloom Filter를 사용해서 빠르게 대충 검사한 다음, 의심이 가는 사이트인 경우 데이터베이스에 다시 정확하게 검사하는 것이죠. 아마 위험 사이트 데이터베이스의 크기가 크고, 검사 요청이 굉장히 빈번하게 일어나기 때문에 Bloom Filter를 전처리 과정으로 사용해서 데이터베이스 요청 부하를 줄이는 것으로 보입니다.

**비트코인**도 [내부적으로 Bloom Filter를 사용하는 것으로 알려져 있습니다.](https://bitcoin.org/en/developer-guide#application-of-bloom-filters)

보통은 Disk IO를 줄이기 위한 최적화 방법으로 많이 사용한다고 하는군요.

# 체험해보기

아래 사이트를 이용하면 Bloom Filter가 어떤 자료 구조인지 웹에서 눈으로 확인해볼 수 있습니다.

[Bloom Filters by Example](https://llimllib.github.io/bloomfilter-tutorial/)

---

저도 Bloom Filter에 대해서 미리 알았더라면 전에 만들던 서비스 구현을 좀 더 효율적으로 할 수 있었을 거란 생각이 드네요.
혹시 저처럼 몰랐던 개발자 분이 계시다면, 한번 찾아보시면 나중에 꼭 도움이 될거라 생각합니다.
읽어주셔서 감사합니다.