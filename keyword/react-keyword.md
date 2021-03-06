# 섹션 3 - react 기초

## 컴포넌트란?

- 사용자 인터페이스에서 재사용할 수 있게 하며, 각각의 요소를 모두 컴포넌트로 나누어 구성하게 되면 유지관리 하기 쉬운 작은 단위의 코드를 가질수 있다.

## JSX 코드

- 자바스크립트 안에 있는 HTML 코드이며, 곧 자바스크립트 XML을 의미한다.

  - 결국 HTML은 XML이라고 할 수 있기 때문이다.

- react의 패키지를 이용하게 되면 자동적으로 브라우저에서 작동하는 코드로 변환된다.

  - 그래서 JS와 HTML 두 코드의 장점인 브라우저에서의 작동과 개발자가 작성하기 쉬운점이 특징이다.

- 복잡한 JSX 코드의 경우에 루트 요소는 여러개가 아닌 하나의 요소여야한다.

## react 작동방식

- react는 실제 화면에 보이는 것을 업데이트하는 DOM 지시를 생성하고 실행하는 역할을 한다.

- 일반적인 JS에서 하던 DOM은 단계별로 요소를 선택하고 추가하고 기능을 선언해야하는 명령형 접근 방식을 따르고 있지만 react에서는 태그나 단락의 최종상태를 정의만 하면 자동으로 화면에 불러오기위한 지시를 내린다.

## CSS 스타일 추가

- react 전체 프로세스가 CSS파일을 인식하도록 선언해야한다.

  - import 'file path 작성'; 을 통해 인식하도록 한다.

-JSX 구문에 html의 class와 같은 개념으로 className을 사용해 태그를 감싸는 클래스를 지정한다.

## JSX에서 동적 데이터 출력

- 일반적인 JS코드에 데이터를 선언하고 JSX 코드안에서 react 구문을 사용한다.

  - JSX 코드안에 {선언한 데이터 상수,변수} 중괄호를 통해 기본적인 JS코드를 실행한다.

## props 통해 데이터 전달

- JS에서 함수를 작성할때 매개변수를 만들어 함수를 재사용할 수 있게 하는데 react에서도 동일한 개념이 적용되기때문에 매개변수를 이용해 재사용할 수있는 컴포넌트를 만들수 있다.

- 속성을 추가하여 지정 컴포넌트 끼리 데이터를 전달할 수 있다.

- 컴포넌트에게 전달되는 props 는 파라미터를 통하여 조회 한다. props 는 객체 형태로 전달되며, 만약 선언되어있는 name 값을 조회하고 싶다면 props.name 을 조회하면 된다.

  - react는 컴포넌트에서 한 개의 매개변수만 사용한다.

## 컴포지션의 개념

- 컴포넌트는 JSX 코드를 결합한 사용자 정의 HTML이고, 스타일링이다. 그리고 원한다면 JS 로직을 추가한다.

- 복잡한 구조의 컴포넌트에서 특정 코드를 추출하여 코드 중복을 피하고, 다른 컴포넌트를 깔끔하게 유지하게 한다.

## 화살표 함수

- cosnt app = () => {}

# react State & event

## State 활용

- import React, { } from 'react'; 중괄호를 추가하여 전반적인 리액트 객체를 임포트가능

- useState 함수: 컴포넌트 함수가 다시 호출되는 곳에서 변경된 값을 반영하기 위해 state로 값을 정의할 수 있게 해주는 함수.

  - useState는 리액트 훅이라고 불리는데 중요한 훅 중 하나이다.

  - 모든 훅은 use로 시작한다.

  - useState는 기본적인 state 값 대신 useState()로 특별한 종류의 변수를 생성한다고 할 수 있다.

  - useState를 사용하여 상태를 등록하면 현재 상태값과 업데이트하는 함수값 두개의 값을 얻는다.

    - state가 변할때마다 업데이트 함수를 호출한다.

## 사용자 입력 listening

- on 으로 시작하는 여러가지 이벤트중 onChange 이벤트의 경우 모든 input 타입과 같은 이벤트를 사용할 수 있다는 장점이 있다.

  - ex) dropdown 메뉴와 같이

## input 태그의 이벤트 함수

- onChange : 변경될 때 마다 실행됨.

  - input 태그에서 [name]: value 값을 가져와 갱신

- onClick : 클릭하면 실행됨.

# 렌더링 리스트 및 조건부 Content

- 데이터 렌더링 리스트

  - 표준 JS의 배열 메소드 map()

    - 다른 배열을 기반으로 새로운 배열 생성, 원본 배열에 있는 요소를 변환한다.

- 조건부 렌더링

  - 특정 조건에 따라 다른 결과물을 렌더링 하는 것

- 효율적인 방법으로 배열의 데이터를 업데이트 하기 위해 map() 함수를 사용한다.

  - 동적인 배열을 렌더링해야 할 때 map을 사용해 일반 데이터 배열을 리액트 엘리멘트로 이루어진 배열로 변환해주면 된다.

# 심화 - fragment 작업, Portals & Refs

## JSX의 제한 사항

- 루트 JSX 요소는 하나만 있어야 하기 때문에 div로 감싸는 방법으로 코드를 작성한다.

- JSX 요소인 배열로 작업을 하면 react는 모든 요소에 대한 key를 필요로 한다.

  - 데이터 리스트 안에서 동적으로 mapping 하고 그 데이터를 JSX요소와 mapping하려면 key가 필수적으로 필요하다.

## wrapper 만들어 div 대신 사용하기

- Wrapper 컴포넌트를 생성하여 props.children을 반환하는 빈 컴포넌트를 만든다.

  - 여기서 props.children은 사용자 정의 컴포넌트에서 여는태그와 닫는 태그 사이에 넣은 모든 내용을 담고 있다.

- 생성한 Wrapper 컴포넌트를 임포트 하여 기존의 div 태그 대신 Wrapper를 사용하여 JSX 요구사항을 충족시키며 작동시킨다.

- 하지만 react가 지원하는 기능인 React.Fragment를 Wrapper를 대신해 사용하면 같은 효과를 내기 때문에 react를 임포트하는 곳에 ,{Fragment} 추가하여 <React.Fragment>를 사용하는게 더욱 편하다.

## Portals

- Portal은 부모 컴포넌트의 DOM 계층 구조 바깥에 있는 DOM 노드로 자식을 렌더링하는 방법이다.

  - 두 개의 인자를 가지는데, 첫 번째 인자는 렌더링할 수 있는 React 자식, 두 번째는 DOM 엘리멘트이다.

  - ReactDOM.createPortal(렌더링되어야하는 React 노드, 요소가 렌더링 되어야하는 실제 DOM 컨테이너를 가리키는 포인터)

## Refs

- Ref는 render 메서드에서 생성된 DOM 노드나 React 엘리먼트에 접근하는 방법이다.
