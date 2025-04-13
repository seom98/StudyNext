### 8강 Page Router

-   폴더 구조로 url 페이지 라우팅이 생김
-   동적 경로(Dynamic Routes)도 쉽게 만들 수 있음
    -   폴더 경로 하위에 [id].js와 같이 생성하면 id라는 동적 경로에 대응하는 페이지 라우팅이 생김

### Page Router 방식의 Next 프로젝트 생성하기

```js
npx create-next-app@14 [프로젝트 이름]
```

-   NPX : Node Package Executor
    -   NPM에 올라가 있는 최신 버전의 노드 패키지를 다운로드 없이 바로 실행시키는 명령어
-   옵션설정에서 Page Router선택
    ![![alt text](image.png)](<page router 방식 세팅.png>)

### Page router

#### \_app.tsx

-   리액트의 App.tsx와 대응되는 파일
-   페이지 컴포넌트와 그 내용들을 받아서 렌더링함
-   App이 최상단으로 그 하위 컴포넌트로 페이지들이 들어가게 됨

#### useRouter

-   query parameter를 불러올 수 있음
-   페이지 라우터 방식의 경우 useRouter를 router에서 불러와야 함
    -   앱 라우터 방식의 경우 navigator에서 불러옴

#### Dynamic Routing

-   query Parameter에 동적인 변수가 들어가는 경우 파일명을 [변수명].tsx로 하면 됨
-   만약 다양한 query를 받는다면 [...변수명].tsx를 하면 됨
    -   이 경우 router의 query에 배열로 저장됨
        => catch all segment라고 함
-   이렇게 한 경우 query parameter가 없는 경우 에러가 뜸
    -   더 범용적으로 사용하고 에러가 안 뜨고 싶으면 [[...변수명]].tsx로 작성하면 됨
        => optional catch all segment 라고 함

#### 에러 페이지

-   404 에러 페이지에 대응하는 페이지의 경우 404.tsx로 만들어주면 됨
