# Vuex

## 개요
- 복잡한 애플리케이션의 컴포넌트들을 효육적으로 관리
- Vuex 라이브러리의 등장 배경 : Flux 패턴
- Vuex 라이브러리의 주요 속성
    - state : data
    - getters : computed
    - mutations : methods
    - actions : 비동기 methods
- Helper 기능을 통해 Vuex를 더 쉽게 코딩할 수 있음

## Vuex란?
- 무수히 많은 컴포넌트의 데이터를 관리하기 위한 상태 관리 패턴이자 라이브러리
- React의 Flux 패턴에서 기인함
- Vue.js 중고급 개발자로 성장하기 위한 필수 관문

## Flux란?
- MVC 패턴의 복잡한 데이터 흐름 문제를 해결하는 개발 패턴(Unidirectional data flow)
    - Action → Dispatcher → Model → View
        - Action : 화면에서 발생하는 이벤트 또는 사용자의 입력
        - Dispatcher : 데이터를 변경하는 방법, 메서드, model을 바꾸기 위한 역할
        - Model : 화면에 표시할 데이터
        - View : 사용자에게 비춰지는 화면

## MVC패턴과 Flux 패턴 비교
- MVC 패턴
    - Controller → Model ↔ View
        - Controller : Model과 View를 제어
        - Model : 화면에 찍혀나오는 데이터를 DB에서 가져왔다면 Model.
        - View : 우리가 보고 있는 화면
    - 데이터 처리를 양방향으로 처리.
    - Model과 View가 n:n일 경우 어떤 버그가 생길 지 예측하기 어려움.
- Flux 패턴
    - Action → Dispatcher → Model → View
    - 데이터의 흐름이 여러 갈래로 나뉘지 않고 단방향으로만 처리 함
    - Safe한(안전한) 코드를 짤 수 있음.


## Vuex가 왜 필요할까?
- 복잡한 애플리케이션에서 컴포넌트의 개수가 많아지면 컴포넌트 간에 데이터 전달이 어려워진다.
- 예시
    - 이벤트 버스 사용 시
        - 어디서 이벤트를 보냈는지 혹은 어디서 이벤트를 받았는지 알기 어려움
            ```javascript
            // Login.vue
            eventBus.$emit('fetch', loginInfo);
            // List.vue
            eventBus.$on('display', data => this.displayOnScreen(data));
            //Chart.vue
            eventBus.$emit('refreshData', chartData);
            ```
        - 컴포넌트 간 데이터 전달이 명시적이지 않음

## Vuex로 해결할 수 있는 문제
1. MVC 패턴에서 발생하는 구조적 오류를 해결 가능
2. 컴포넌트 간 데이터 전달 명시
3. 여러 개의 컴포넌트에서 같은 데이터를 업데이트 할 때 동기화 문제

## Vuex 컨셉
- State : 컴포넌트 간에 공유하는 데이터 data()
- View : 데이터를 표시하는 화면 template
- Action : 사용자의 입력에 따라 데이터를 변경하는 methods
- View → Action → State → View → Action → State → ....(단방향 삼각형 구조)

## Vuex 구조
- 컴포넌트 → 비동기 로직 → 동기 로직 → 상태 ....(단방향 사각형 구조)

## Vuex 기술요소
- state : 여러 컴포넌트에 공유되는 데이터 `data`
- getters : 연산된 state 값을 접근하는 속성 `computed`
- mutations : state 값을 변경하는 이벤트 로직·메서드 `methods`
- actions : 비동기 처리 로직을 선언하는 메서드 `async methods`