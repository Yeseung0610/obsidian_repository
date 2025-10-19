---
tags:
  - 컨퍼런스
  - Flutter
---

### 1. Flutter 기술 번역, AI 리뷰어와 함께 완성하기
##### 유경욱 | Flutter Seoul

**Flutter Enginnering**
- 저자. 마지드 하지안
- Flutter의 랜더링, 상태관리, Widget의 Render Tree등 중급의 내용을 많이 다루고 있음.
##### 초벌 번역 이후 문제점
기술서의 경우 오역을 하거나, 맥락을 다르게 작성하게되면 기술적인 내용이 달라질 수 있기 때문에, 문제가 될 수 있음 > AI를 활용한 번역을 투트랙으로 진행함


##### 사례: 용어 선택 토론
Persistence Layer를 어떻게 번역할까?
- 문제 상황 : 영속 계층으로 번역했지만, 현업에서는 퍼시스턴트 계층으로 사용되어 고민이 되었음
- AI 답변 : 영속 계층이 JPA등 업계 표준, 공식 문서에서 사용되는 표준 용어이므로 번역서에 더 적합함

##### AI 보완 엔지니어링 워크플로우
1. **초벌 번역**
   Human-led Drafting: 전문가 (나)가 1차 결과물을 완성하며  맥락과 뉘앙스를 장악
2. **의심 영역 식별**
   Identity Uncertatinties: 용어, 기술적 정확성, 문제 등 불확실한 부분을 마킹
3. **목표 지향적 질의**
   Targeted Probing: 설계된 질문으로 AI 리뷰어에게 검토를 요청
4. **비판적 수용 및 최종 결정**
   Critical Adoption: AI의 제안을 맹신하지 않고, 비판적으로 검토해 최종 결정을 내리는 것은 나의 몫

---

### 2. Less state, More flutter
##### nine | Flutter Seoul

**소셜 네트워킹 애플리케이션에서 상태관리 Library없이 State less 방식으로 위젯을 관리한 경험 공유**
- 해당 기능이 필요했던 이유
	- 3초 길이의 짧은 숏폼 비디오를 제공함
	- Gifs와 같이 리소스를 많이 사용하는 이미지
	- 영상 하나로 30~40%의 CPU가 사용되는데,이 상황에서 영상 코멘트, 스티커 등이 올라갈 경우 CPU가 100% 점유율을 찍게 됨

##### 문제 상황
- 비디오가 백그라운드 환경에서도 계속 동작함
- 해결 : Navigator를 사용하여, video 매니지먼트를 Navigator 이동에 따라 자동으로 pause, play 처리하도록 함
- 사용한 함수 : didPushNext()
- 제한 사항 : 비디오가 있는 페이지 기준이 아닌 비디오를 기준으로 동작하여야함


RouteAware


---

### 3. Why MapLIbre: Flexibility and the Freedom to Unlock Full Potential in Flutter Apps with Maps
##### Ryutaro Iseki : YUMEMI Inc.

- **현재 개발 중인 서비스**
	- 전세계에 있는 음식에 대한 유저의 기록을 남기게 하는 애플리케이션

현재 사용 중인 map 라이브러리 : maplibre_gl


--- 

### 4. AI Debate Club
##### Sasha Denisov | EPAM

##### Server Based AI
- REST API
- Open SDK (Only can use supported platform)

##### Edge AI
- **Firebase Vertex AI**
	- Gemini API
	- Imagen API
- **GGUF + llama.cpp**
	- Plugin llama_cpp_dart
	- Plugin llama_cpp

##### Server Based AI vs Edge AI

|           | Server Based AI                          | Edge AI     |
| --------- | ---------------------------------------- | ----------- |
| Price     | EC2 월 사용량<br>AI Token 비용<br>아웃바운드 트래픽 비용 | AI Token 비용 |
| Analytics | 기본 제공 X, 자체 구현 필요                        | 기본 제공 O     |

---

### 5. Riverpod 3.0
##### Remi Rouseelet | Author of Riverpod

##### Mutations
현재 Store로 처리하고 있는 상태들을 Mutations으로 정리하도록 리팩토링하면 깔끔하게 Single tone 구조를 사용할 수 있을 것으로 생각 됨

##### NotifierProvider.retry
retry 기능을 Automatic하게 관리할 수 있는 callback 함수로 보여짐. 추후 확인 필요

#### 상태 관리
- **StreamProvider**
	- watch 중인 consumer가 있는지 없는지 여부에 따라 자동으로 pause/resume 상태를 전환하는 것으로 보여짐
	- 상태 관리에 용이하며, 메모리를 절약할 수 있다
- **Notifier.build**
	- build 함수 호출 시 provider는 Recreated된다. (새로운 인스턴스로 재생성)
- **Provider의 상태관리**