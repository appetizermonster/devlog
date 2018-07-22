---
layout: post
title: Bash 쉘 스크립팅 - If 문
---

저는 게임이나 안드로이드 앱, 웹 어플리케이션을 만든 경험은 꽤 있지만 서버 사이드 어플리케이션을 만든 경험은
많지 않습니다. 그래서 유닉스 계열 운영체제를 사용한 경험도 많지 않습니다. 그런데 최근에 서버 사이드 어플리케이션을
만들게 되면서 유닉스 CLI 환경에서 작업을 많이 하고 있습니다.

쉘 스크리팅에 대해서 그다지 큰 관심을 가지고 있지 않았는데, 최근에 CLI 환경에서 작업을 많이 하다보니까 이게 꽤 편리한 것 같더라고요.
그래서 제 자신도 공부할 겸 **Bash 쉘 스크립팅**에 대해서 정리해보려고 합니다.

오늘은 한번 `If 구문(If Statements)`에 대해서 정리해보겠습니다.

---

`If 구문`은 거의 모든 프로그래밍 언어에서 사용할 수 있는 기본적인 기능입니다. `If 구문`을 이용하면 프로그램의 분기를 만들 수 있습니다.
Bash 또한 `If`문을 지원하고, 단순 비교 외에 다양한 기능을 추가로 제공합니다.

## 문자열 비교

```bash
VAR1="abc"

if [ $VAR1 == "abc" ]; then
  echo "$VAR1 is abc"
else
  echo "$VAR1 is not abc"
fi
```

위 스크립트는 Bash에서의 기본적인 If/Else 문을 사용한 예제입니다.

## 파일 비교
