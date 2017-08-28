---
layout: post
title: 정렬 알고리즘 - 거품 정렬 (Bubble sort)
date: 2017-07-23 02:32:54 +0000
---

지금까지 제가 대충 알고만 있었던 기본적인 프로그래밍 지식을 정리해보려고 합니다.

오늘은 거품 정렬 (Bubble sort)에 대해서 정리해보겠습니다.
거품 정렬은 배열을 정렬하는 방법으로, **인접한 두 개의 원소를 비교하여**, 마지막 원소부터 점진적으로 정렬해나가는 방법입니다.

## 알고리즘
<center><img src="https://upload.wikimedia.org/wikipedia/commons/5/54/Sorting_bubblesort_anim.gif" style="max-width:100%;">
</center>

거품 정렬을 이용해서 배열을 오름차순으로 정렬하는 알고리즘은 다음과 같습니다:
1. `첫번째 원소`와 `두번째 원소`를 비교합니다.
2. `두번째 원소`가 가 더 큰 경우, 두 원소를 서로 교환(Swap)합니다.
3. 위 과정을 `마지막 원소`를 만날 때까지 실행합니다.
4. 위 과정을 모두 마치고 나면 `마지막 원소`는 가장 큰 값이 되어있습니다.
5. 값이 정해진 `마지막 원소`를 제외하고 1~4번 과정을 다시 반복합니다.

## 거품 정렬의 핵심
거품 정렬의 핵심은 하나의 사이클(1~4 과정)을 수행할 때마다 마지막 원소를 가장 큰 값(내림차순의 경우 가장 작은 값)으로 만든다는 것입니다. 그리고 이 과정을 계속 반복하면 배열을 정렬된 상태로 만들 수 있습니다.

## 구현
JavaScript를 이용해서 오름차순 거품 정렬을 다음과 같이 구현할 수 있습니다.
```javascript
let array = [4, 3, 2, 1]

for (let n = array.length - 1; n > 0; --n) {
  for (let i = 0; i < n; ++i) {
    if (array[i] < array[i+1])
      swap(array[i], array[i+1])
  }
}
```

## 시간 복잡도
거품 정렬의 시간 복잡도는 `O(n^2)`입니다. 한마디로 **느립니다**.
크기 `n`인 배열을 거품 정렬을 이용해서 정렬하면 `(n-1)+(n-2)+(n-3)+...+1`번의 비교 연산을 하게 됩니다.
비교 연산의 횟수는 등차수열의 합을 이용해서 `n(n-1)/2`로 표현할 수 있습니다.
그리고 이를 시간 복잡도로 표현하면 `O(n^2)`으로 표현할 수 있습니다.

## 최적화
거품 정렬은 한번의 사이클이 실행될 때 교환(Swap)이 일어나지 않는 경우, 이미 정렬이 완료된 것으로 판단할 수 있기 때문에 루프를 중단(break)해서 더 이상 불필요한 정렬을 실행하지 않을 수 있습니다.

---
거품 정렬은 굉장히 느린 편에 속하는 정렬 알고리즘이기 때문에 충분히 작은 크기의 데이터를 정렬할 때를 제외하고는 잘 사용되지 않습니다.
하지만 정렬의 기본이고, 구현이 굉장히 쉽기 때문에 프로그래머라면 알아두는게 좋을 것 같습니다.
감사합니다.