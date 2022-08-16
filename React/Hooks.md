# Hooks

### Hooks
React conf 2018에 발표

 💪 Hooks는 함수 컴포넌트에서 사용할 수 없었던 state, refs, context, side effects 처리 등과 같은 React의 콘셉을 보다 직관적으로 사용할 수 있는 API를 제공.
 
 #### 로직 재사용

오늘날 React 앱에서 로직을 재사용하는 방법은 많디. 일반적인 재사용 방법은 함수 혹은 클래스를 작성하고 호출하는 것. 
그리고 React는 함수, 클래스를 사용해 컴포넌트를 작성한다. 

하지만 컴포넌트 내부에 캡슐화 된 로직은 다른 컴포넌트와 공유가 쉽지 않다. 
결국 로직을 재사용하기 위해 React 앱에서 [Render Props](https://ko.reactjs.org/docs/render-props.html), [HOC](https://ko.reactjs.org/docs/higher-order-components.html)와 같은 복잡한 패턴을 사용해야 함. 
함수의 로직을 다른 함수로 공유하는 데 최소한의 노력만을 필요로 하지만 함수는 내부에서 상태(state)를 관리 할 수 없는 문제를 가진다.

-> 🙌🏻 이러한 문제는 Hooks을 통해 해결할 수 있다.  


#### 캡슐화

Hook은 완전하게 캡슐화 처리되므로, 현재 실행 중인 컴포넌트에서 Hook을 호출할 때에도 격리된 로컬 상태를 유지 
Hook은 상태를 공유하는 방법이 아니라, **상태 저장 로직을 공유하는 방법**
결과적으로 Hook은 React의 단방향 데이터 흐름을 깨트리지 않는다❕

#### 클린 트리

Hook 간에 데이터를 전달하는 기능은 Hooks를 애니메이션, 구독, 폼 관리 등을 처리하는데 매우 적합 
Hooks는 컴포넌트에 연결된 메모리 셀(memory cell)의 단순한 리스트와 유사하다.

#### 상태 유지 위치

React가 Hooks에 대한 상태를 유지하는 위치는 React가 클래스 컴포넌트 상태를 유지하는 방법과 똑같은 위치에 유지한다. 
React에는 컴포넌트를 어떻게 정의하든 관계없이 모든 상태에 대한 내부 업데이트 대기열이 있다.

[React hooks: not magic, just arrays](https://medium.com/@ryardley/react-hooks-not-magic-just-arrays-cd4f1857236e)

#### 보다 작은 번들 크기
Hooks는 클래스를 사용할 때 보다 번들된 파일의 크기를 줄임!

#### 사용 규칙
1. React 함수 컴포넌트, 다른 커스텀(사용자 정의) Hook 함수 안에서만 사용 가능. 
일반 함수, 또는 클래스 컴포넌트 안에서 호출 ✖.
2. Hook은 문 또는 중첩 된 함수 안에서 사용할 수 없다. 
(컴포넌트, 커스텀 Hook 함수 최상위에서만 사용)



## useState 훅

함수 컴포넌트에서 상태를 관리할 때는 **React.useState()** 훅을 사용❗ 


#### 상태 값, 업데이트 함수

useState() 훅은 상태와 상태 업데이트를 담당하는 함수를 반환. 
훅에 최초 전달된 값이 컴포넌트의 초기 상태 값이 되며, 함수 컴포넌트가 다시 렌더링 될 때는 항상 이전의 업데이트 된 상태 값이 최신 상태 값이 된다.

```jsx
const [stateValue, stateUpdater] = useState(initialState);
```

[useState API](https://ko.reactjs.org/docs/hooks-reference.html#usestate)



#### 지연된 초기화

`initialState` 인자는 함수 컴포넌트 초기 렌더링 시에만 사용되는 `state` 초깃값을 설정. 
이후 다시 렌더링 될 때는 이 값이 무시된다. 하지만 `state` 초깃값을 계산하는데 많은 시간이 필요한 경우 컴포넌트를 사용할 때마다 지연되는 문제가 발생한다.

```jsx
**// 계산에 적지 않은 시간이 소요될 경우: 약 790.62890625 ms**
const [fibo39] = useState(**fibonacci(39)**);
```

이 문제는 지연된 초기화(초기 렌더링 시에만 실행될 함수 설정)를 사용해 해결가능.

```jsx
const [fibo39] = useState(**() => {
	// 최초 1회만 고비용 계산이 처리된 후, 메모(기억)된 값을 다시 사용
  // 처리 시간: 약 790.62890625 ms
	const initialState = fibonacci(39);

	// 계산 이후: 지연된 초기화의 처리 값을 반환
	return initialState;
}**);
```

<aside>
☝ localStorage에서 데이터 값을 읽어오는 경우에도 지연된 초기화 방법을 사용할 수 있다.

```jsx
const [persnalization] = useState(() => {
	**const persnalization = localStorage.getItem('persnalization');
	return JSON.parse(persnalization);**
});
```

</aside>

[지연 초기 state](https://ko.reactjs.org/docs/hooks-reference.html#lazy-initial-state)


[고비용의 객체를 지연해서 생성하는 법?](https://ko.reactjs.org/docs/hooks-faq.html#how-to-create-expensive-objects-lazily)





#### 객체 타입 상태 관리

useState() 훅에서 클래스의 state, setState()와 동일하게 작동되도록 하려면 합성된 객체를 반환해야 한다.

```jsx
const [state, updateState] = useState({
	key1: false,
	key2: true
});

**// 업데이트 방법 1 (객체)
updateState({
  ...state,
  key1: true,
});**

**// 업데이트 방법 2 (함수)**
**updateState(prevState => ({
  ...prevState, 
  key1: true
}));**
```

<aside>
❕ useState()는 상태를 합성하는 것이 아니라, 대체한다.
클래스 컴포넌트의 setState 메서드와 다르게, 이전 상태를 새로운 상태가 대체함.
</aside>

[Hooks API Reference - React 함수 활용](https://ko.reactjs.org/docs/hooks-reference.html#functional-updates)
[Hook 자주 묻는 질문 - React 하나 또는 여러 state 변수를 사용해야 합니까?](https://ko.reactjs.org/docs/hooks-faq.html#should-i-use-one-or-many-state-variables)
[Using the State Hook - React 상태 병합이 아닌, 대체](https://ko.reactjs.org/docs/hooks-state.html#tip-using-multiple-state-variables)
[Hook 자주 묻는 질문 - React 상태 “병합”을 설정하는 방법](https://ko.reactjs.org/docs/hooks-faq.html#should-i-use-one-or-many-state-variables)


## useEffect 훅

함수 컴포넌트에서 발생 가능한 부수 효과(Side Effects)는 **React.useEffect** 훅으로 관리❗.

```jsx
useEffect(effectCallback);
```

#### 이펙트 함수

사이드 이펙트(비동기 통신 요청/응답, DOM 조작, 구독/취소 등)는 class 컴포넌트의 render 메서드에서는 다룰 수 없다. 
이를 다룰 수 있는 라이프 사이클 메서드 내에서만 다뤄야 한다. 
useEffect() 훅은 class 컴포넌트의 사이드 이펙트 관리 라이프 사이클 메서드 기능을 모두 처리❕.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/455f3b4b-c564-4b85-8d36-65c59a5af3e5/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/455f3b4b-c564-4b85-8d36-65c59a5af3e5/Untitled.png)

함수 컴포넌트의 본문은 class 컴포넌트의 render 메서드에 해당되므로 사이드 이펙트 코드를 포함할 수 없지만 
useEffect() 훅에 전달 된 함수 내부에서는 사이드 이펙트를 작성할 수 있다. 전달 된 함수는 React 요소가 실제 DOM에 렌더링 된 이후 콜백(실행) 된다.

```jsx
useEffect(() => {
	// DOM 마운트(렌더링) 이후 콜백(실행)
});
```

[Using the Effect Hook - React **관심사 구분, 멀티 이펙트 활용**](https://ko.reactjs.org/docs/hooks-effect.html#tip-use-multiple-effects-to-separate-concerns)


#### 이펙트 조건 처리

특정 조건에 따라 이펙트 함수를 실행해야 할 경우, useEffect() 훅의 2번째 인자로 종속성 배열을 설정한다.

```jsx
useEffect(
	() => {
		// componentDidMount
	}, 
	**[]**
);
```

종속성 배열에 관리할 상태가 추가되면, 해당 상태가 변경될 때에만 이펙트 함수가 실행된다. (조건 처리)

```jsx
useEffect(
	() => {
		// componentDidMount
		// componentDidUpdate
	}.
	**[...dependencies]**
);
```

[Using the Effect Hook - React **Effect를 건너뛰어 성능 최적화하기**](https://ko.reactjs.org/docs/hooks-effect.html#tip-optimizing-performance-by-skipping-effects)



#### 클린업

이펙트 함수를 통해 설정된 사이드 이펙트(예: 구독 등)는 컴포넌트가 UI에서 제거될 때 정리되어야 한다. 
이를 수행하려면 이펙트 함수에서 클린업 함수를 반환하고 그 함수 내부에서 정리를 실행한다.

```jsx
useEffect(
	() => {
		// 구독
		**return () => {
			// 정리(cleanup) 함수
			// 구독 취소
		}**
	},
	[]
);
```

<aside>
클린업(Cleanup) 함수는 [메모리 누수](https://ko.wikipedia.org/wiki/%EB%A9%94%EB%AA%A8%EB%A6%AC_%EB%88%84%EC%88%98)(Memory Leak) 방지를 위해 UI에서 컴포넌트를 제거하기 직전 수행된다. 
이는 class 컴포넌트의 componentWillUnmount와 유사하게 동작한다고 볼 수 있지만, 실상은 다음 이펙트 함수가 실행될 때마다 클린업 함수가 먼저 실행되어 정리.

</aside>

[Using the Effect Hook - React](https://ko.reactjs.org/docs/hooks-effect.html#effects-with-cleanup)

클린업(clean up) 함수

[Using the Effect Hook - React](https://ko.reactjs.org/docs/hooks-effect.html#explanation-why-effects-run-on-each-update)

렌더링 될 때 마다 클린업 함수가 실행되는 이융

---

#### useLayoutEffect 훅

useEffect() 훅과 사용법이 동일한 useLayoutEffect() 〰
차이점은 실행되는 시기👂
페이지 로드 차단을 방지하기 위해 DOM이 렌더링 된 이후 useEffect() 훅에 설정된 콜백함수가 실행되면 위치 및 스타일 적용에 문제가 발생할 수 있다. 
이러한 문제를 해결해야 할 경우 useLayoutEffect() 훅을 사용한다.

**useLayoutEffect() 훅은 DOM이 렌더링 되고 페인팅 되기 직전에 실행된다. 
반면, useEffect는 DOM 페인팅 이후 실행된다.**

```jsx
useLayoutEffect(() => {
	// 컴포넌트 렌더링 시마다 실행
});

useLayoutEffect(() => {
	// 초기 마운트 과정 이후 1회 실행
}, []);

useLayoutEffect(() => {
	// 의존하는 상태 값이 업데이트 될 때 마다 실행
}, [state]);
```

- **useEffect vs. useLayoutEffect 훅**
    
    ```jsx
    function LayoutShift() {
    
      const effectRef = useRef(null);
      useEffect(() => {
        const { current: target } = effectRef;
        target.style.top = 0;
        target.style.left = '50%';
        target.style.transform = 'translate(-50%, 0)';
      }, []);
    
      const layoutEffectRef = useRef(null);
      **useLayoutEffect(() => {
        const { current: target } = layoutEffectRef;
        target.style.bottom = 0;
        target.style.left = '50%';
        target.style.transform = 'translate(-50%, 0)';
      }, []);**
    
      return (
        <>
          <Box ref={effectRef} className="effect">
            Effect
          </Box>
    
          **<Box ref={layoutEffectRef} className="layout-effect">
            Layout Effect
          </Box>**
    
          {[...Array(15000).keys()].map((idx) => {
            return (
              <p
                key={idx}
                css={`
                  position: absolute;
                  bottom: 0;
                `}
              />
            );
          })}
        </>
      );
    }
    ```
    
    ![Aug-13-2021 10-02-19.gif](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/540f779b-20ce-4be4-9eef-7f4d140bcd8c/Aug-13-2021_10-02-19.gif)
    

[Hooks API Reference - React useLayoutEffect 훅](https://ko.reactjs.org/docs/hooks-reference.html#uselayouteffect)



---



