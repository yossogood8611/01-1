#Next.js 개발 환경 구축
리액트 어플리케이션의 서버렌더링을 구현하기 위한 Next.js 공부 

##Next.js란?
리액트 어플리케이션의 서버사이드렌더링을 쉽게 구현할 수 있게 도와주는 간단한 프레임워크이다.

###개발 환경 구축
```
cd my-app
yarn init -y
yarn add react react-dom next
mkdir pages
```

###페이지 라우팅
1. 컴포넌트 생성 - hello.js
2. Index 페이지에 링크 - <Link href="/hello"> </Link>
