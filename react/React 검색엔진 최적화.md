# React 검색엔진 최적화(SEO)

---

## 단일 페이지 응용 프로그램(SPA)

- 단일 페이지 애플리케이션은 데스크탑 애플리케이션과 유사한 사용자 경험을 제공한다.
- SPA에서 js로 페이지를 작성하기 때문에 실제 body는 비어있다고 인식한다.
- 검색 엔진 최적화를 하는 방법은 다음이 있다.

## Next.js (SSR)

---

### 서버 사이드 렌더링(SSR)의 장점

1. 서버에서 클라이언트 대신 렌더링을 해 주면 검색 엔진이 페이지의 내용을 제대로 수집할 수 있다.
2. 초기 렌더링 기능을 개선할 수 있다. (파일 다운로드 전에도 html상에 볼 수 있는 컨텐츠 존재)

### 핵심기능

1. 코드 스플리팅

    route와 component 각각을 분리하여 페이지별로 내려받는다.

2. 클라이언트 사이드 라우팅

    Router, Link 모두 imort 가능

3. 커스텀 API 서버

    커스텀 서버를 생성해서 as의 URL이 href를 바라볼 수 있게 처리를 해줘야 새로고침, 뒤로 갔을 때도 랜더링이 가능해진다.

4.  getInitialProps()

    React의 ComponentDidMount는 렌더링이 두 번 되는 반면, 데이터를 미리 갖고 오기 때문에 한 번에 렌더링이 가능하다.

단점 : 컴포넌트 기반으로 라우트를 설정하는 리액트 라우터와는 다르게, 파일 시스템에 기반하여 라우트를 설정하기 때문에 원래의 리액트를 Next.js로 구현하기 까다롭다.

[Next.js 제대로 알고 쓰자](https://medium.com/@msj9121/next-js-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%95%8C%EA%B3%A0-%EC%93%B0%EC%9E%90-8727f76614c9)

## Razzle (SSR)

---

1. 리액트 라우터와도 잘 호환되는 도구이다.
2. 최신버전의 Loadable Component를 커스텀하기는 힘들다.
3. 자료를 찾기가 힘들다.

## 서버 사이드 렌더링 직접 구현

---

1. 서버 사이드 렌더링 전용 웹팩 환경 설정
2. 빌드 스크립트 작성
3. 서버 코드 작성
4. 정적 파일 제공
5. redux-thunk 코드 사용
6. Users, UsersContainer 컴포넌트 사용
7. PreloadContext 작성
8. 서버에서 리덕스 설정 및 PreloadContext 사용
9. ...

많고 번거로운 작업을 통해 구현 원리를 알고 직접 구현하는 방법이다.

## React-helmet (CSR)

---

브라우저가 JS를 받아와 동적으로 렌더링한다.

1. react-helmet 을 이용하여 태그를 동적으로 제어
    - react-helmet 패키지

        JSX내부의 Helmet 컴포넌트를 이용하여 메타태그 관리

2. react-router-dom 패키지를 이용하여 페이지별 메타태그 적용
3. react-snap을 이용하여 페이지 별 index.html 파일 생성

header의 메타 태그를 수정할 수 있어, 검색 엔진에 잡힐 수는 있지만, 크롤링을 하면 아무것도 읽히지 않는다. 보통 다른 SSR을 도입할 수 없을 때 쓰는 방법.

[SPA에서 서버사이드 렌더링을 구축하지 않고 SEO 최적화하기](https://velog.io/@byseop/SPA%EC%97%90%EC%84%9C-%EC%84%9C%EB%B2%84%EC%82%AC%EC%9D%B4%EB%93%9C-%EB%A0%8C%EB%8D%94%EB%A7%81%EC%9D%84-%EA%B5%AC%EC%B6%95%ED%95%98%EC%A7%80-%EC%95%8A%EA%B3%A0-SEO-%EC%B5%9C%EC%A0%81%ED%99%94%ED%95%98%EA%B8%B0)

## 그 외에 알게된 점

---

### React와 비슷한 GatsbyJS

- JS가 실행되면 빈 HTML 페이지 안에 마크업을 추가해주는 SPA와는 다르게, 개발 후 Build 과정에서 마크업이 생성된다.
- 단순히 static 페이지를 만들어주는 것으로 끝나는 것이 아니라, 필요에 따라 CSR과 SSR, lazy loading을 적절히 섞어 사용할 수 있다.
- 콘텐츠를 Markdown으로 관리(JAMstack)하기 때문에 비교적 쉽게 콘텐츠를 관리할 수 있다.
- GatsbyJS의 유용한 Plugin
    - **[gatsby-plugin-react-helmet](https://www.gatsbyjs.org/packages/gatsby-plugin-react-helmet)**: meta tag를 쉽게 바꿀 수 있음
    - **[gatsby-plugin-robots-txt](https://www.gatsbyjs.org/packages/gatsby-plugin-robots-txt/)**: **`robot.txt`** 자동 생성
    - **[gatsby-plugin-sitemap](https://www.gatsbyjs.org/packages/gatsby-plugin-sitemap/)**: 빌드 시 sitemap 자동 생성
    - **[gatsby-plugin-canonical-urls](https://www.gatsbyjs.org/packages/gatsby-plugin-canonical-urls/)**: canonical 이슈 해결
