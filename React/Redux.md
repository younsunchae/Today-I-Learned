[리덕스 공식 홈페이지](https://ko.redux.js.org/introduction/getting-started/) <br/>

[벨로퍼트의 Redux](https://velopert.com/3528)

# Redux

리액트의 상태 관리 라이브러리 <br/>

리덕스를 쓰면 상태 관리를 컴포넌트에 종속시키지 않고, 컴포넌트의 바깥에서 관리할 수 있음.

![](https://i.imgur.com/nWgg01Z.png) <br/>

부모에 종속되어 있는 컴포넌트의 상태 관리를 <br/>

![](https://i.imgur.com/c6A4cHg.png) <br/>

리덕스 스토어에서 관리할 수 있다. <br/>

컴포넌트가 스토어에 구독을 하면 소토어의 상태값에 변동이 생길 때 전달받았던 함수를 호출한다. <br/>

리덕스는 리액트에 종속되어 있는 라이브러리가 아니기 때문에 다른 환경에서도 사용 가능!

## Redux Toolkit

Redux의 문제점

1. 복잡한 store 설정
2. Redux를 사용하기 위한 다른 라이브러리 추가 설치
3. 너무 많은 양의 보일러 플레이트 반복작성
   <br/>

Redux의 단점들을 제거한 Redux에서 공식적으로 내놓은 `패키지` <br/>

해결 방안

1. configureStore 함수를 통한 store 설정
2. 두 가지 패키지 설치
