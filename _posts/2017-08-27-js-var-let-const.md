---
layout: post
title: JavaScript - var, let, const
---

ES5 이전의 JavaScript에서는 변수를 선언하기 위해서 `var` 키워드만을 사용했다.  
그런데 ES6(2015) 이후의 JavaScript에서는 변수 선언을 위한 키워드 두 개가 추가되었다. `let`과 `const` 키워드이다.

## const

`const` 키워드를 사용한 변수 선언의 특징은 아래 예제처럼 비교적 명확하다.

```javascript
const a = 'A';

a = 'B'; // 에러!
```

`const`를 이용해서 변수를 선언하면 그 변수를 더 이상 수정할 수 없게 된다.  
정확히는 assignment만 금지되므로, 아래와 같은 작업은 가능하다.

```javascript
const a = [];
const b = {};

a.push(0);       // OKAY!
b['new'] = 'a';  // OKAY!
```

위 예제들을 통해서 `const`에 대해서는 쉽게 이해할 수 있게 되었다. 하지만 `let`은 무슨 목적으로 만들어진걸까?  

[WIP]
