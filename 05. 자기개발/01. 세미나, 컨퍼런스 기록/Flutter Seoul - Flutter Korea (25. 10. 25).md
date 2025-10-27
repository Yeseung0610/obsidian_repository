---
tags:
  - 컨퍼런스
  - Flutter
  - Developments
  - MobileApp
---

### 1. Thorvg 패키지 오픈소스 기여 경험
##### 권태형 | 고려대학교

**Lottie vs Thorvg**
- Lottie는 Flutter의 렌더링 엔진에서 동작하며, 랜더링 성능 최적화에 제약이 있음
- Thorvg는 자체 엔진을 통해 렌더링 후, CustomPainter를 통해 Flutter 엔진 위에 띄우는 방식임

**오픈소스 기여 경험**
- 오픈소스에 기여할 때 OS는 Linux, Mac을 사용했음 (해당 OS의 선택 과정은 thorvg 패키지에서의 특성이기에 각 오픈소스 별로 사용하면 좋은 OS는 다를 수 있음)

**첫 번째 PR #25 (기여 경험)**
- https://github.com/thorvg/thorvg.flutter/pull/25


**두 번째 Issue #26 (실수 사례)**
- https://github.com/thorvg/thorvg.flutter/issues/26
- gitignore 와 같이 작은 부분에 대해 기여를 하는 것에 만족감을 느끼지 못해 해당 이슈를 보고함
- "1 week expected", "If you can assign this hob for me" 등 신뢰가 쌓이지 않은 상태에서 작업을 제의하는 것은 프로젝트의 방향성과 옳지 않을 수 있음

**세 번째 PR #29 (실패 경험)**
- https://github.com/thorvg/thorvg.flutter/pull/29
- FFI 관련 지식에 대한 공부와 각 플랫폼 별로 정적 링킹에 관한 부분에 해결하기 어려운 이슈를 만남
- 어떤 문제가 있었는지, 어떤 부분들을 시도했었는지 이후 기여자를 위해 기록한 후 PR을 닫음

**네 번째 PR #31 (장점을 살린 기여 경험)**
- https://github.com/thorvg/thorvg.flutter/pull/31
- 스스로 배경지식을 토대로 이슈 보고 > 문제 해결 > 기여를 경험
- Flutter의 FinalRenderObject와 WidgetBindings.addPostFrameCallback을 사용해 문제 해결