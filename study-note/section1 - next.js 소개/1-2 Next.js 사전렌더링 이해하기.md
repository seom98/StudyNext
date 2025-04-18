## 사전 렌더링

#### 브라우저의 요청에 사전에 렌더링이 완료된 HTML을 응답하는 렌더링 방식

-   유저가 브라우저에 초기 접속 요청을 하면 웹 서버 측에서 JS를 실행(렌더링)해서 HTML 컨텐츠로 모두 변환하여 완료된 HTML을 클라이언트에 보내줌
    -   Client Side Rendering의 단점을 효율적으로 해결
        ![![alt text](image.png)](<사전 렌더링 동작.png>)

<br>

#### 어떻게 CSR의 단점을 보완할까?

-   CSR은 브라우저에게 웹 서버가 기초 틀 역할을 하던 빈껍데기 index.html 화면을 보내주고 브라우저는 우선 화면에 빈 화면을 렌더링함
    ![![alt text](image.png)](<CSR 동작.png>)
-   그 동안 작성해놓았던 JS Bundle(모든 페이지의 코드)을 후속으로 받아오고 클라이언트가 직접 실행함
    -   이 때가 되어서야 유저가 내용들을 확인할 수 있음 => 브라우저가 할 일이 많아서 초기 접속 화면이 표현되는 게 느림 (FCP가 늦어짐)
        -   **FCP(First Contentful Paint)** : 요청 시작 시점으로부터 컨텐츠가 화면에 처음 나타나는데 걸리는 시간
    -   대신 초기 접속 이후 화면 이동이 빠름

<br>

### 사전 렌더링 동작 과정

![![alt text](image.png)](<사전 렌더링 동작.png>)

-   화면에 렌더링 : HTML 코드를 브라우저가 화면에 그려내는 작업
-   JS 실행(렌더링) : 자바스크립트 코드(React 컴포넌트)를 HTML로 변환하는 과정
-   아직 HTML 코드만 받아서 상호작용이 불가능
    ![![alt text](image.png)](hydration.png)
-   JS bundle을 가져와서 JS를 실행하여 HTML과 연결하게 됨
    -   이를 hydration이라고 함
    -   이렇게 상호작용이 가능해지는 시점을 TTI(Time To Interactive)라고 함

<br>

### 페이지 이동

![![alt text](image.png)](<페이지 이동.png>)

-   컴포넌트를 교체하는 식으로 페이지 이동이 되게 됨
-   JS Bundle의 경우 리액트 앱

<br>

#### 리액트 단점 해소

-   사전 렌더링을 통해 빠른 FCP 달성 -> 리액트 단점 해소
-   React App의 장점 승계 -> 빠른 페이지 이동
