# React component 정리
react component를 공부한 후 개념과 응용방법을 정리하기 위한 자료이다.


## 현재 프로젝트의 진행 양상과 리액트 공부 방향
전에 진행하던 프로젝트에서 반응형 웹을 제대로 구현하지 못한 아쉬움에서 이번 프로젝트에 반응형 웹을 구현할 뿐 아니라, 새로운 프레임워크인 react를 써보기로 했다.
여태껏 여러가지로 관심만 많았던 프론트엔드를 제대로 공부해보고 싶었고 최대한 많은 기술을 공부하여 적용할 것이다. 회의 도중 프로젝트의 특성에 따라 Server Side Rendering을 쓰기로 했다. SSD를 구현하려면 redux와 router 부분에서 next.js를 사용한다고 해서 next.js를 공부하기 전에 react component에 대한 개념을 정리해보려 한다.


### React component의 개념
리액트의 핵심적인 요소. 컴포넌트는 MVC의 뷰를 독립적으로 구성하여 재사용을 가능하게 하고 컴포넌트를 통해 새 컴포넌트를 쉽게 만들 수 있다.


### 컴포넌트 구성 요소
1. 프로퍼티
  - 상위 컴포넌트에서 하위 컴포넌트로 전달되는 읽기 전용 데이터
  - 속성(attribute) 형태로 전달되는 값
  - 컴포넌트 내부에서 값을 바꿀 수 없음
  - 하위 컴포넌트에서 this.props.name 으로 참조 가능
  - 단방향 데이터 흐름
  - 다양한 자료형으로 전달 가능함 (배열, 객체)
  - 필수 프로퍼티 지정, 기본값 지정 가능함
2. state
  - 컴포넌트의 상태를 저장하고 변경할 수 있는 데이터
  - 보통 이벤트와 함께 사용
  - 생성자에서 반드시 초기화해야 함
  - state 값을 변경할 때 반드시 setState() 함수를 사용해야 함
  - setState() 함수는 비동기로 처리, setState() 코드 이후로 연결된 함수들의 실행이 완료될 때 화면 동기화 과정 거침
  - 함수가 호출될 때마다 새롭게 화면을 출력하고 싶으면 forceUpdate() 함수 사용
3. 컨텍스트
  - 부모 컴포넌트에서 생성하여 모든 자식 컴포넌트에 전달하는 데이터
  - 컴포넌트 간의 자료 의존성 없어지게 함
  - 공급자, 소비자 존재 (단방향 데이터 흐름)
  - 사실 뒷부분 공부를 안해서 내용을 아직 잘 모름


### 생명주기함수
컴포넌트의 생성부터 소멸까지의 과정을 컴포넌트의 생명주기라 한다.
이 함수들로 특정 시점에 원하는 동작을 하도록 만들 수 있다.
constructor(props), render(). static getDerivedStateFromProps(props, state), componentDidMount(), shouldComponentUpdate(nextProps, nextState), getSnapshotBeforeUpdate(prevProps, prevState), componentDidUpdate(prevProps, preState, snapshot), componentWillUnmount() 순으로 있다.


### 클래스형 / 함수형 컴포넌트
함수형 컴포넌트는 state가 없다. Stateless Functional Component(SFC).
state와 생명주기 함수를 사용할 수 없어서 단순한 구조의 UI 컴포넌트를 제작할 때 많이 사용된다.
하지만 2019년부터 함수형 컴포넌트에 리액트 훅(hook)을 지원해주어서 공식 문서에서 함수형 컴포넌트를 권장한다.
여태까지 내가 알아본 훅을 이용한 함수형 컴포넌트는
  1. 그동안 클래스형 컴포넌트에서만 할 수 있었던 state 관리와 생명주기함수를 사용할 수 있게 되었다
  2. 클래스형 함수의 복잡성, 재사용성 문제를 해결한다
  3. useState() 훅을 이용하면 shallow copy(얕은 복사)때문에 항상 새로운 객체로 전달해줘야 하는 복잡함을 해결할 수 있다(원하는 값을 인자로 전달하면 됨)
  4. react hooks API를 이용하면 된다 (useState() 함수는 대표적인 react hooks API)
와같은 특징들이 있다.


### 함수형 컴포넌트 틀

```
import React from 'react';

function App() {
  const name = props;
  return (
    ...
  );
}

export default App;
```

### 앞으로 공부 계획
react와 next.js 문법을 공부해서 9월 후반에 간단한 실습을 해봐야 실제 프로젝트 투입 전에 만족할만한 실력이 그나마 갖춰질 것 같다.
페이지 레이아웃 + 상세디자인, react&next.js 공부를 9월안에 끝내야해서 조금 급할수 있겠지만 일을 키워놓은 만큼 책임지고 할 일 열심히 해야겠다.









