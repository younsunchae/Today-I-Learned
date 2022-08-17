# CSR vs SSR

### 클라이언트 사이드 렌더링

클라이언트 측 렌더링은 페이지 요청이 브라우저에서 이뤄지고, 
웹 사이트를 구성할 HTML, JavaScript 파일을 서버로부터 전송 받는다. 
이후 JavaScript를 사용해 HTML 콘텐츠를 생성하는 렌더링 모드❕

이 방법은 매 페이지 마다 HTML 페이지를 렌더링 하기 위해 서버로부터 응답 받지 않아도 되므로, 보다 현대적인 렌더링 방법. 
기술적인 관점에서 이 모드는 서버에 요청하는 부담을 덜어 클라이언트 측의 프로세스를 보다 빠르게 만들어 준다.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/259158fb-5e53-457c-be53-e4e11098d155/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/259158fb-5e53-457c-be53-e4e11098d155/Untitled.png)

- **장점 (cons)**
    
    서버로부터 요청/응답 과정 없이 웹 브라우저에서 렌더링 하는 방법이라, 페이지 렌더링 시마다 서버에 요청/응답 받을 필요가 없어 서버 측 렌더링 보다 훨씬 빠르다. 
    그에 따라 사용자 경험 또한 크게 향상❕
    
- **단점 (Pros)**
    
    JavaScript를 기반으로 클라이언트 측에서 렌더링하기 때문에 검색 엔진이 이를 인식하지 못할 경우, 웹 사이트가 검색에 잘 노출되지 않은 문제를 보일 수 있다. 
    게다가 클라이언트 측 렌더링 방식은 앱 모듈 최적화가 안된 경우, 첫 페이지 방문 시 늦게 표시될 수 있다. (모듈 번들링 최적화 필요)
    
 
### 서버 사이드 렌더링

서버 측 렌더링은 클라이언트 측 렌더링 보다 오래되고 무거운 것으로 간주되기도... 
사용자가 웹 사이트에서 서버에 요청하면 요청 정보가 서버에 전송되고, 서버는 요청에 응답하는 HTML 코드가 포함된 파일을 생성해 전송한다. 

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c6f56d0f-5ae5-4493-bf1a-18432a4882de/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c6f56d0f-5ae5-4493-bf1a-18432a4882de/Untitled.png)

- **장점 (cons)**
    
    검색 엔진에 최적화 ❕
    이 방법으로 구성된 페이지는 훨씬 더 많은 트래픽을 유도하고 검색 순위에도 잘 노출된다.
    
    SEO와 관련하여 SSR의 또 다른 장점은 페이지의 보다 빠른 인덱싱 ❕
    알고리즘이 콘텐츠를 감지하고 더 짧은 시간에 순위를 매긴다.
    
    첫 페이지 로딩은 서버에서 생성된 HTML 코드를 포함한 파일이 전송되므로 CSR 보다 빠르다 ❕
    
- **단점 (Pros)**
    
    SSR의 첫 페이지 렌더링이 빨라도 다른 페이지를 탐색하는 사용자 경험은 CSR 보다 느리다. 
    페이지 탐색 시마다 서버에 요청해야 하고, 서버에서 HTML 코드를 포함한 파일을 생성해 전송 받아야 하기 때문이다. 
    이 방법은 모든 사용자의 활동 정보를 서버에서 관리(축적)해야 해 서버의 부담이 더 크다.
    
    ‼ 결과적으로 서버에서 담당하는 것이 많아지므로 보다 높은 수요가 발생할 경우 더 많은 비용이 듭니다.
    

[Client-side rendering vs. server-side rendering: which one is better](https://rockcontent.com/blog/client-side-rendering-vs-server-side-rendering/)

[Client-side rendering vs. server-side rendering](https://medium.com/@adamzerner/client-side-rendering-vs-server-side-rendering-a32d2cf3bfcc)

[[번역] Client-side rendering VS. Server-sde rendering](https://jongmin92.github.io/2017/06/06/JavaScript/client-side-rendering-vs-server-side-rendering/)


## 싱글 페이지 앱 (SPA)
실습

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/df9ec1b2-9964-4c32-9c4a-e0e81f6f582a/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/df9ec1b2-9964-4c32-9c4a-e0e81f6f582a/Untitled.png)

<aside>
☝ public/index.html 페이지가 랜딩(Landing) 된 이후, 클라이언트 환경에서 라우팅이 이뤄진다. 
즉, 다른 페이지를 렌더링 하기 위해 서버에 요청

</aside>

- **MPA vs. SPA**
    
    멀티 페이지 앱은 사용자 요청에 의해 다른 페이지를 서버에서 생성하여 응답 받는다. 
    반대로 싱글 페이지 앱은 첫 페이지 렌더링 이후, 다른 페이지 렌더링 시 서버에서 페이지를 만들어 오지 않는다.
    
    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/aa1b7418-5b9b-4020-b9f3-d1c66996571e/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/aa1b7418-5b9b-4020-b9f3-d1c66996571e/Untitled.png)
    
    **참고**
    
    [Single-page App vs. Multi-page App: Pros, Cons, and Which is Better?](https://lvivity.com/single-page-app-vs-multi-page-app)
    

### 패키지 설치

React 앱을 클라이언트 환경에서 라우팅 하기 위한 라이브러리로 React Router를 사용.

```bash
npm i react-router-dom@6
```

[React Router](https://reactrouter.com/docs/en/v6/getting-started/installation#basic-installation)

Basic Installation

### 라우터 연결

클라이언트 사이드 라우팅은 BrowserRouter 컴포넌트를 불러와 앱을 감싸는 것에서 시작.

**src/index.js**

```jsx
import 'styles/index.css';
import { StrictMode } from 'react';
import { render } from 'react-dom';
import WireframeApp from 'wireframe/App';
**import { BrowserRouter as Router } from 'react-router-dom';**

/* -------------------------------------------------------------------------- */

render(
  <StrictMode>
    **<Router>**
      <WireframeApp />
    **</Router>**
  </StrictMode>,
  document.getElementById('root')
);
```

<aside>
☝ [HashRouter](https://reactrouter.com/docs/en/v6/api#hashrouter)를 사용하면 HTML5 History API 대신, 해시(`#`)를 사용해 라우팅 

</aside>

[React Router](https://reactrouter.com/docs/en/v6/api#browserrouter)

BrowserRouter 컴포넌트

### 내비게이션 링크 설정

애플리케이션을 탐색할 수 있도록 NavLink 컴포넌트를 불러와 사용합니다. (`to`, `className` prop 설정)

**src/components/Navigation/Navigation.js**

```jsx
Navigation.Item = function ({ item, currentPage, ...restProps }) {
  return (
    <li className={styles.item} {...restProps}>
      **<NavLink
        to={item.href}
        className={({ isActive }) => {
          return !isActive
            ? styles.link
            : classNames(styles.link)(styles.active);
        }}
      >**
        {item.text}
      **</NavLink>**
    </li>
  );
};
```

[React Router](https://reactrouter.com/docs/en/v6/api#navlink)

NavLink 컴포넌트

### 라우트 구성

**src/wireframe/App.js**

Routes, Route 컴포넌트를 사용해 경로(path)에 따라 페이지 엘리먼트(JSX)를 렌더링 하도록 구성합니다.

<aside>
🎙️ useRouter 훅을 걷어내고, useState 훅을 사용해 navigation 상태를 추가합니다. 그리고 `currentPage` prop 또한 연결된 모든 컴포넌트에서 제거합니다.

</aside>

- **코드 풀이**
    
    ```jsx
    import styles from './App.module.css';
    import { Header, Main, Footer } from 'containers';
    import { Navigation } from 'components';
    **import { useState } from 'react';**
    **import { Routes, Route } from 'react-router-dom';**
    **import { Dashboard, Landing, Products } from 'pages';**
    
    /* ----------------------------------------------------------------------- */
    
    export default function WireframeApp() {
    
      **const [navigation] = useState([
        { id: 'landing', href: '/', text: '홈' },
        { id: 'products', href: '/products', text: '프로덕트' },
        { id: 'dashboard', href: '/dashboard', text: '대시보드' },
      ]);**
    
      return (
        <div className={styles.wireframe}>
          <Header className="wireframeBox">
            <Navigation list={navigation} />
          </Header>
          <Main>
            **<Routes>
              <Route path="/" element={<Landing />} />
              <Route path="/dashboard" element={<Dashboard />} />
              <Route path="/products" element={<Products />} />
            </Routes>**
          </Main>
          <Footer>
            <div className="wireframeBox" />
          </Footer>
        </div>
      );
    }
    ```
    
    [useRoutes](https://reactrouter.com/docs/en/v6/api#useroutes) 
    훅을 사용하는 방법도 Routes 컴포넌트를 사용해 라우트를 구성하는 것과 기능적으로는 동일 
    다만, Route 컴포넌트 대신 JavaScript 객체를 사용해 라우트를 구성할 수 있다.
    
    ```jsx
    function WireframeApp() {
    
      const [navigation] = useState([
        { id: 'landing', href: '/', text: '홈' },
        { id: 'dashboard', href: '/dashboard', text: '대시보드' },
        { id: 'products', href: '/products', text: '프로덕트' },
      ]);
    
      **const routeElements = useRoutes([
        { path: '/', element: <Landing /> },
        { path: '/dashboard', element: <Dashboard /> },
        { path: '/products', element: <Products /> },
      ]);**
    
      return (
        <div className={styles.wireframe}>
          <Header className="wireframeBox">
            <Navigation list={navigation} />
          </Header>
          <Main>**{routeElements}**</Main>
          <Footer>
            <div className="wireframeBox" />
          </Footer>
        </div>
      );
    }
    ```
    
    **참고**
    
    [React Router](https://reactrouter.com/docs/en/v6/api#routes-and-route)
    
    [React Router](https://reactrouter.com/docs/en/v6/api#useroutes)
    

### 콘텐츠 바로가기 이동

Link 컴포넌트를 사용해 바로 메인 콘텐츠 영역으로 이동할 수 있도록 구성 (접근성 고려)

- **코드 풀이**
    
    ```jsx
    import styles from './SkipToContent.module.css';
    import { createPortal } from 'react-dom';
    **import { useLocation } from 'react-router-dom';**
    import { string } from 'prop-types';
    import { A11yHidden, Link } from 'components';
    import { classNames } from 'utils';
    
    /* -------------------------------------------------------------------------- */
    
    export function SkipToContent({
      targetId,
      className,
      label,
      ...restProps
    }) {
    
      const {pathname} = useLocation();
    
      return createPortal(
        <A11yHidden
          as={Link}
          **to={`${pathname}#${targetId}`}**
          className={classNames(`${styles.container} focusable`)(className)}
          {...restProps}
        >
          {label}
        </A11yHidden>,
        document.getElementById('skip-to-content')
      );
    }
    
    SkipToContent.defaultProps = {
      targetId: 'content',
      label: '메인 영역으로 이동',
    };
    
    SkipToContent.propTypes = {
      targetId: string,
      className: string,
      label: string,
    };
    ```
    
    **참고**
    
    ["Skip Navigation" Links](https://webaim.org/techniques/skipnav/)
    
    [How to Create a "Skip to Content" Link](https://css-tricks.com/how-to-create-a-skip-to-content-link/)
