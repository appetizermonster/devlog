---
layout: post
title: 서버 관리를 엄청나게 줄여주는 AWS Elastic Beanstalk을 아시나요?
date: 2017-07-05 02:08:21 +0000
---

<img src="https://steemitimages.com/DQmRt8zrD16YmS1qNB5N7CvcURAh8YG4X6WwMTo3Dtmha5w/image.png" style="max-width:100%;">

개발자라면 아마존에서 제공하는 클라우드 서비스 [AWS(Amazon Web Services)](https://aws.amazon.com/)에 대해서 많이들 들어보셨을텐데요.
아마 **S3 (스토리지)**, **EC2 (가상 서버)**에 대해서는 많이 아실텐데, [Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/)에 대해서는 잘 모르시는 분들이 많을 것 같아요.
저 또한 그랬고요 ㅠㅠ 이걸 몰라서 조사하고 세팅하는데 낭비한 시간이 꽤 많았던 것 같습니다.
그래서 이것에 대해서 적어보려고 합니다.

## Amazon Web Services
아마존닷컴은 단순히 물건 파는 사이트가 아닙니다. 세계 1위의 클라우드 서비스 제공업체입니다.
AWS는 아마존닷컴이 제공하는 클라우드 서비스 이름입니다. 서버로 할 수 있는 거의 모든 것을 임대해주고 있습니다.
가상 서버, 스토리지, 데이터베이스, 메시지큐, API Gateway 등등 말이죠.
[넷플릭스](https://www.netflix.com/)나 [드랍박스](https://www.dropbox.com/) 같은 덩치 큰 회사 뿐만 아니라 엄청나게 많은 IT 업체들이 AWS를 이용했거나 이용하고 있습니다.

## EC2
EC2는 AWS에서 제공하는 가장 기본적으로 제공하는 가상 서버를 임대해주는 서비스입니다. 서버를 임대받고 나면 SSH를 이용해 원격으로 접속해서 사용자 마음대로 조작할 수 있습니다. 자유도가 큰 만큼 관리가 귀찮다는 단점이 있습니다.
어플리케이션도 내가 설치해야 하고, 모니터링도 내가 알아서 해야하는 거죠.
AWS에서 제공하는 많은 서비스들이 내부적으로는 EC2를 이용하는 경우가 많습니다. 그만큼 AWS의 핵심인 서비스라고 볼 수 있습니다.

# [Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/)?

<img src="https://d0.awsstatic.com/video-thumbs/ElasticBeanstalk_Thumbnail.png" style="max-width:100%;">

EC2가 자유롭게 서버를 조작할 수 있게 해줬던 서비스라면, Elastic Beanstalk은 그 자유도를 제한하고 편리성을 엄청나게 증가시킨 서비스입니다.
사용자가 서버에서 실행할 어플리케이션(예: Node.js로 만든 웹 어플리케이션, Python으로 만든 봇)을 업로드하면 나머지는 Elastic Beanstalk이 알아서 해주는 서비스입니다. (내부적으로 EC2를 이용합니다.)
서버도 알아서 올리고, 프로그램도 자동으로 실행시켜 주고 관리해주는 거죠. 사용자는 파일 올리고 버튼만 누르면 됩니다.

<center>
<img src="http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/images/gettingstarted-dashboard.png" style="max-width:100%;">
Elastic Beanstalk 대시보드
</center>

아래와 같은 기능을 제공합니다.

- Go, Java, Node.js, PHP, Python, Ruby, .NET, Docker 등 지원
- 내가 원하는 사양의 서버 선택 가능
- 사용량 증가에 따라서 자동으로 스케일링 되게 설정 가능 (서버 갯수 자동 조절)
- 서버 사용량 모니터링 제공 (트래픽, CPU, 메모리 사용량 등)
- 웹 어플리케이션의 경우 로드 밸런싱 제공 (nginx를 리버스 프록시로 제공합니다)
- 점진적 배포 지원 (여러 개의 서버를 사용하는 앱의 업데이트를 점진적으로 가능하게 해줍니다)

결과적으로 Elastic Beanstalk을 사용하면 내 컴퓨터에서 웹 어플리케이션을 만들어서 테스트하고, SSH를 이용한 서버 관리 없이 웹에서 바로 어플리케이션을 배포하고 관리할 수 있습니다. 엄청 편리합니다.
서버에 이상이 있는 경우 메일로 경고가 날라오고요. (AWS SNS를 이용하면 메신저를 이용해서 받아볼 수도 있습니다)

EC2만 썼을 때는 왜 사람들이 AWS가 편리하다고 하는지 몰랐었는데, Elastic Beanstalk을 사용하면서 AWS의 생태계를 다 경험해보니까
왜 AWS가 최고인건지 느낄 수 있었습니다.
혹시 작은 규모의 팀에서 웹 서비스를 준비중이시라면 [AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/)을 한번 찾아보시길 추천드립니다.
감사합니다.