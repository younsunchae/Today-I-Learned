# Hooks

### Hooks
React conf 2018์ ๋ฐํ

 ๐ช Hooks๋ ํจ์ ์ปดํฌ๋ํธ์์ ์ฌ์ฉํ  ์ ์์๋ state, refs, context, side effects ์ฒ๋ฆฌ ๋ฑ๊ณผ ๊ฐ์ React์ ์ฝ์์ ๋ณด๋ค ์ง๊ด์ ์ผ๋ก ์ฌ์ฉํ  ์ ์๋ API๋ฅผ ์ ๊ณต.
 
 #### ๋ก์ง ์ฌ์ฌ์ฉ

์ค๋๋  React ์ฑ์์ ๋ก์ง์ ์ฌ์ฌ์ฉํ๋ ๋ฐฉ๋ฒ์ ๋ง๋. ์ผ๋ฐ์ ์ธ ์ฌ์ฌ์ฉ ๋ฐฉ๋ฒ์ ํจ์ ํน์ ํด๋์ค๋ฅผ ์์ฑํ๊ณ  ํธ์ถํ๋ ๊ฒ. 
๊ทธ๋ฆฌ๊ณ  React๋ ํจ์, ํด๋์ค๋ฅผ ์ฌ์ฉํด ์ปดํฌ๋ํธ๋ฅผ ์์ฑํ๋ค. 

ํ์ง๋ง ์ปดํฌ๋ํธ ๋ด๋ถ์ ์บก์ํ ๋ ๋ก์ง์ ๋ค๋ฅธ ์ปดํฌ๋ํธ์ ๊ณต์ ๊ฐ ์ฝ์ง ์๋ค. 
๊ฒฐ๊ตญ ๋ก์ง์ ์ฌ์ฌ์ฉํ๊ธฐ ์ํด React ์ฑ์์ [Render Props](https://ko.reactjs.org/docs/render-props.html), [HOC](https://ko.reactjs.org/docs/higher-order-components.html)์ ๊ฐ์ ๋ณต์กํ ํจํด์ ์ฌ์ฉํด์ผ ํจ. 
ํจ์์ ๋ก์ง์ ๋ค๋ฅธ ํจ์๋ก ๊ณต์ ํ๋ ๋ฐ ์ต์ํ์ ๋ธ๋ ฅ๋ง์ ํ์๋ก ํ์ง๋ง ํจ์๋ ๋ด๋ถ์์ ์ํ(state)๋ฅผ ๊ด๋ฆฌ ํ  ์ ์๋ ๋ฌธ์ ๋ฅผ ๊ฐ์ง๋ค.

-> ๐๐ป ์ด๋ฌํ ๋ฌธ์ ๋ Hooks์ ํตํด ํด๊ฒฐํ  ์ ์๋ค.  


#### ์บก์ํ

Hook์ ์์ ํ๊ฒ ์บก์ํ ์ฒ๋ฆฌ๋๋ฏ๋ก, ํ์ฌ ์คํ ์ค์ธ ์ปดํฌ๋ํธ์์ Hook์ ํธ์ถํ  ๋์๋ ๊ฒฉ๋ฆฌ๋ ๋ก์ปฌ ์ํ๋ฅผ ์ ์ง 
Hook์ ์ํ๋ฅผ ๊ณต์ ํ๋ ๋ฐฉ๋ฒ์ด ์๋๋ผ, **์ํ ์ ์ฅ ๋ก์ง์ ๊ณต์ ํ๋ ๋ฐฉ๋ฒ**
๊ฒฐ๊ณผ์ ์ผ๋ก Hook์ React์ ๋จ๋ฐฉํฅ ๋ฐ์ดํฐ ํ๋ฆ์ ๊นจํธ๋ฆฌ์ง ์๋๋คโ

#### ํด๋ฆฐ ํธ๋ฆฌ

Hook ๊ฐ์ ๋ฐ์ดํฐ๋ฅผ ์ ๋ฌํ๋ ๊ธฐ๋ฅ์ Hooks๋ฅผ ์ ๋๋ฉ์ด์, ๊ตฌ๋, ํผ ๊ด๋ฆฌ ๋ฑ์ ์ฒ๋ฆฌํ๋๋ฐ ๋งค์ฐ ์ ํฉ 
Hooks๋ ์ปดํฌ๋ํธ์ ์ฐ๊ฒฐ๋ ๋ฉ๋ชจ๋ฆฌ ์(memory cell)์ ๋จ์ํ ๋ฆฌ์คํธ์ ์ ์ฌํ๋ค.

#### ์ํ ์ ์ง ์์น

React๊ฐ Hooks์ ๋ํ ์ํ๋ฅผ ์ ์งํ๋ ์์น๋ React๊ฐ ํด๋์ค ์ปดํฌ๋ํธ ์ํ๋ฅผ ์ ์งํ๋ ๋ฐฉ๋ฒ๊ณผ ๋๊ฐ์ ์์น์ ์ ์งํ๋ค. 
React์๋ ์ปดํฌ๋ํธ๋ฅผ ์ด๋ป๊ฒ ์ ์ํ๋  ๊ด๊ณ์์ด ๋ชจ๋  ์ํ์ ๋ํ ๋ด๋ถ ์๋ฐ์ดํธ ๋๊ธฐ์ด์ด ์๋ค.

[React hooks: not magic, just arrays](https://medium.com/@ryardley/react-hooks-not-magic-just-arrays-cd4f1857236e)

#### ๋ณด๋ค ์์ ๋ฒ๋ค ํฌ๊ธฐ
Hooks๋ ํด๋์ค๋ฅผ ์ฌ์ฉํ  ๋ ๋ณด๋ค ๋ฒ๋ค๋ ํ์ผ์ ํฌ๊ธฐ๋ฅผ ์ค์!

#### ์ฌ์ฉ ๊ท์น
1. React ํจ์ ์ปดํฌ๋ํธ, ๋ค๋ฅธ ์ปค์คํ(์ฌ์ฉ์ ์ ์) Hook ํจ์ ์์์๋ง ์ฌ์ฉ ๊ฐ๋ฅ. 
์ผ๋ฐ ํจ์, ๋๋ ํด๋์ค ์ปดํฌ๋ํธ ์์์ ํธ์ถ โ.
2. Hook์ ๋ฌธ ๋๋ ์ค์ฒฉ ๋ ํจ์ ์์์ ์ฌ์ฉํ  ์ ์๋ค. 
(์ปดํฌ๋ํธ, ์ปค์คํ Hook ํจ์ ์ต์์์์๋ง ์ฌ์ฉ)



## useState ํ

ํจ์ ์ปดํฌ๋ํธ์์ ์ํ๋ฅผ ๊ด๋ฆฌํ  ๋๋ **React.useState()** ํ์ ์ฌ์ฉโ 


#### ์ํ ๊ฐ, ์๋ฐ์ดํธ ํจ์

useState() ํ์ ์ํ์ ์ํ ์๋ฐ์ดํธ๋ฅผ ๋ด๋นํ๋ ํจ์๋ฅผ ๋ฐํ. 
ํ์ ์ต์ด ์ ๋ฌ๋ ๊ฐ์ด ์ปดํฌ๋ํธ์ ์ด๊ธฐ ์ํ ๊ฐ์ด ๋๋ฉฐ, ํจ์ ์ปดํฌ๋ํธ๊ฐ ๋ค์ ๋ ๋๋ง ๋  ๋๋ ํญ์ ์ด์ ์ ์๋ฐ์ดํธ ๋ ์ํ ๊ฐ์ด ์ต์  ์ํ ๊ฐ์ด ๋๋ค.

```jsx
const [stateValue, stateUpdater] = useState(initialState);
```

[useState API](https://ko.reactjs.org/docs/hooks-reference.html#usestate)



#### ์ง์ฐ๋ ์ด๊ธฐํ

`initialState` ์ธ์๋ ํจ์ ์ปดํฌ๋ํธ ์ด๊ธฐ ๋ ๋๋ง ์์๋ง ์ฌ์ฉ๋๋ `state` ์ด๊น๊ฐ์ ์ค์ . 
์ดํ ๋ค์ ๋ ๋๋ง ๋  ๋๋ ์ด ๊ฐ์ด ๋ฌด์๋๋ค. ํ์ง๋ง `state` ์ด๊น๊ฐ์ ๊ณ์ฐํ๋๋ฐ ๋ง์ ์๊ฐ์ด ํ์ํ ๊ฒฝ์ฐ ์ปดํฌ๋ํธ๋ฅผ ์ฌ์ฉํ  ๋๋ง๋ค ์ง์ฐ๋๋ ๋ฌธ์ ๊ฐ ๋ฐ์ํ๋ค.

```jsx
**// ๊ณ์ฐ์ ์ ์ง ์์ ์๊ฐ์ด ์์๋  ๊ฒฝ์ฐ: ์ฝ 790.62890625 ms**
const [fibo39] = useState(**fibonacci(39)**);
```

์ด ๋ฌธ์ ๋ ์ง์ฐ๋ ์ด๊ธฐํ(์ด๊ธฐ ๋ ๋๋ง ์์๋ง ์คํ๋  ํจ์ ์ค์ )๋ฅผ ์ฌ์ฉํด ํด๊ฒฐ๊ฐ๋ฅ.

```jsx
const [fibo39] = useState(**() => {
	// ์ต์ด 1ํ๋ง ๊ณ ๋น์ฉ ๊ณ์ฐ์ด ์ฒ๋ฆฌ๋ ํ, ๋ฉ๋ชจ(๊ธฐ์ต)๋ ๊ฐ์ ๋ค์ ์ฌ์ฉ
  // ์ฒ๋ฆฌ ์๊ฐ: ์ฝ 790.62890625 ms
	const initialState = fibonacci(39);

	// ๊ณ์ฐ ์ดํ: ์ง์ฐ๋ ์ด๊ธฐํ์ ์ฒ๋ฆฌ ๊ฐ์ ๋ฐํ
	return initialState;
}**);
```

<aside>
โ localStorage์์ ๋ฐ์ดํฐ ๊ฐ์ ์ฝ์ด์ค๋ ๊ฒฝ์ฐ์๋ ์ง์ฐ๋ ์ด๊ธฐํ ๋ฐฉ๋ฒ์ ์ฌ์ฉํ  ์ ์๋ค.

```jsx
const [persnalization] = useState(() => {
	**const persnalization = localStorage.getItem('persnalization');
	return JSON.parse(persnalization);**
});
```

</aside>

[์ง์ฐ ์ด๊ธฐ state](https://ko.reactjs.org/docs/hooks-reference.html#lazy-initial-state)


[๊ณ ๋น์ฉ์ ๊ฐ์ฒด๋ฅผ ์ง์ฐํด์ ์์ฑํ๋ ๋ฒ?](https://ko.reactjs.org/docs/hooks-faq.html#how-to-create-expensive-objects-lazily)





#### ๊ฐ์ฒด ํ์ ์ํ ๊ด๋ฆฌ

useState() ํ์์ ํด๋์ค์ state, setState()์ ๋์ผํ๊ฒ ์๋๋๋๋ก ํ๋ ค๋ฉด ํฉ์ฑ๋ ๊ฐ์ฒด๋ฅผ ๋ฐํํด์ผ ํ๋ค.

```jsx
const [state, updateState] = useState({
	key1: false,
	key2: true
});

**// ์๋ฐ์ดํธ ๋ฐฉ๋ฒ 1 (๊ฐ์ฒด)
updateState({
  ...state,
  key1: true,
});**

**// ์๋ฐ์ดํธ ๋ฐฉ๋ฒ 2 (ํจ์)**
**updateState(prevState => ({
  ...prevState, 
  key1: true
}));**
```

<aside>
โ useState()๋ ์ํ๋ฅผ ํฉ์ฑํ๋ ๊ฒ์ด ์๋๋ผ, ๋์ฒดํ๋ค.
ํด๋์ค ์ปดํฌ๋ํธ์ setState ๋ฉ์๋์ ๋ค๋ฅด๊ฒ, ์ด์  ์ํ๋ฅผ ์๋ก์ด ์ํ๊ฐ ๋์ฒดํจ.
</aside>

[Hooks API Reference - React ํจ์ ํ์ฉ](https://ko.reactjs.org/docs/hooks-reference.html#functional-updates)
[Hook ์์ฃผ ๋ฌป๋ ์ง๋ฌธ - React ํ๋ ๋๋ ์ฌ๋ฌ state ๋ณ์๋ฅผ ์ฌ์ฉํด์ผ ํฉ๋๊น?](https://ko.reactjs.org/docs/hooks-faq.html#should-i-use-one-or-many-state-variables)
[Using the State Hook - React ์ํ ๋ณํฉ์ด ์๋, ๋์ฒด](https://ko.reactjs.org/docs/hooks-state.html#tip-using-multiple-state-variables)
[Hook ์์ฃผ ๋ฌป๋ ์ง๋ฌธ - React ์ํ โ๋ณํฉโ์ ์ค์ ํ๋ ๋ฐฉ๋ฒ](https://ko.reactjs.org/docs/hooks-faq.html#should-i-use-one-or-many-state-variables)


## useEffect ํ

ํจ์ ์ปดํฌ๋ํธ์์ ๋ฐ์ ๊ฐ๋ฅํ ๋ถ์ ํจ๊ณผ(Side Effects)๋ **React.useEffect** ํ์ผ๋ก ๊ด๋ฆฌโ.

```jsx
useEffect(effectCallback);
```

#### ์ดํํธ ํจ์

์ฌ์ด๋ ์ดํํธ(๋น๋๊ธฐ ํต์  ์์ฒญ/์๋ต, DOM ์กฐ์, ๊ตฌ๋/์ทจ์ ๋ฑ)๋ class ์ปดํฌ๋ํธ์ render ๋ฉ์๋์์๋ ๋ค๋ฃฐ ์ ์๋ค. 
์ด๋ฅผ ๋ค๋ฃฐ ์ ์๋ ๋ผ์ดํ ์ฌ์ดํด ๋ฉ์๋ ๋ด์์๋ง ๋ค๋ค์ผ ํ๋ค. 
useEffect() ํ์ class ์ปดํฌ๋ํธ์ ์ฌ์ด๋ ์ดํํธ ๊ด๋ฆฌ ๋ผ์ดํ ์ฌ์ดํด ๋ฉ์๋ ๊ธฐ๋ฅ์ ๋ชจ๋ ์ฒ๋ฆฌโ.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/455f3b4b-c564-4b85-8d36-65c59a5af3e5/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/455f3b4b-c564-4b85-8d36-65c59a5af3e5/Untitled.png)

ํจ์ ์ปดํฌ๋ํธ์ ๋ณธ๋ฌธ์ class ์ปดํฌ๋ํธ์ render ๋ฉ์๋์ ํด๋น๋๋ฏ๋ก ์ฌ์ด๋ ์ดํํธ ์ฝ๋๋ฅผ ํฌํจํ  ์ ์์ง๋ง 
useEffect() ํ์ ์ ๋ฌ ๋ ํจ์ ๋ด๋ถ์์๋ ์ฌ์ด๋ ์ดํํธ๋ฅผ ์์ฑํ  ์ ์๋ค. ์ ๋ฌ ๋ ํจ์๋ React ์์๊ฐ ์ค์  DOM์ ๋ ๋๋ง ๋ ์ดํ ์ฝ๋ฐฑ(์คํ) ๋๋ค.

```jsx
useEffect(() => {
	// DOM ๋ง์ดํธ(๋ ๋๋ง) ์ดํ ์ฝ๋ฐฑ(์คํ)
});
```

[Using the Effect Hook - React **๊ด์ฌ์ฌ ๊ตฌ๋ถ, ๋ฉํฐ ์ดํํธ ํ์ฉ**](https://ko.reactjs.org/docs/hooks-effect.html#tip-use-multiple-effects-to-separate-concerns)


#### ์ดํํธ ์กฐ๊ฑด ์ฒ๋ฆฌ

ํน์  ์กฐ๊ฑด์ ๋ฐ๋ผ ์ดํํธ ํจ์๋ฅผ ์คํํด์ผ ํ  ๊ฒฝ์ฐ, useEffect() ํ์ 2๋ฒ์งธ ์ธ์๋ก ์ข์์ฑ ๋ฐฐ์ด์ ์ค์ ํ๋ค.

```jsx
useEffect(
	() => {
		// componentDidMount
	}, 
	**[]**
);
```

์ข์์ฑ ๋ฐฐ์ด์ ๊ด๋ฆฌํ  ์ํ๊ฐ ์ถ๊ฐ๋๋ฉด, ํด๋น ์ํ๊ฐ ๋ณ๊ฒฝ๋  ๋์๋ง ์ดํํธ ํจ์๊ฐ ์คํ๋๋ค. (์กฐ๊ฑด ์ฒ๋ฆฌ)

```jsx
useEffect(
	() => {
		// componentDidMount
		// componentDidUpdate
	}.
	**[...dependencies]**
);
```

[Using the Effect Hook - React **Effect๋ฅผ ๊ฑด๋๋ฐ์ด ์ฑ๋ฅ ์ต์ ํํ๊ธฐ**](https://ko.reactjs.org/docs/hooks-effect.html#tip-optimizing-performance-by-skipping-effects)



#### ํด๋ฆฐ์

์ดํํธ ํจ์๋ฅผ ํตํด ์ค์ ๋ ์ฌ์ด๋ ์ดํํธ(์: ๊ตฌ๋ ๋ฑ)๋ ์ปดํฌ๋ํธ๊ฐ UI์์ ์ ๊ฑฐ๋  ๋ ์ ๋ฆฌ๋์ด์ผ ํ๋ค. 
์ด๋ฅผ ์ํํ๋ ค๋ฉด ์ดํํธ ํจ์์์ ํด๋ฆฐ์ ํจ์๋ฅผ ๋ฐํํ๊ณ  ๊ทธ ํจ์ ๋ด๋ถ์์ ์ ๋ฆฌ๋ฅผ ์คํํ๋ค.

```jsx
useEffect(
	() => {
		// ๊ตฌ๋
		**return () => {
			// ์ ๋ฆฌ(cleanup) ํจ์
			// ๊ตฌ๋ ์ทจ์
		}**
	},
	[]
);
```

<aside>
ํด๋ฆฐ์(Cleanup) ํจ์๋ [๋ฉ๋ชจ๋ฆฌ ๋์](https://ko.wikipedia.org/wiki/%EB%A9%94%EB%AA%A8%EB%A6%AC_%EB%88%84%EC%88%98)(Memory Leak) ๋ฐฉ์ง๋ฅผ ์ํด UI์์ ์ปดํฌ๋ํธ๋ฅผ ์ ๊ฑฐํ๊ธฐ ์ง์  ์ํ๋๋ค. 
์ด๋ class ์ปดํฌ๋ํธ์ componentWillUnmount์ ์ ์ฌํ๊ฒ ๋์ํ๋ค๊ณ  ๋ณผ ์ ์์ง๋ง, ์ค์์ ๋ค์ ์ดํํธ ํจ์๊ฐ ์คํ๋  ๋๋ง๋ค ํด๋ฆฐ์ ํจ์๊ฐ ๋จผ์  ์คํ๋์ด ์ ๋ฆฌ.

</aside>

[Using the Effect Hook - React](https://ko.reactjs.org/docs/hooks-effect.html#effects-with-cleanup)

ํด๋ฆฐ์(clean up) ํจ์

[Using the Effect Hook - React](https://ko.reactjs.org/docs/hooks-effect.html#explanation-why-effects-run-on-each-update)

๋ ๋๋ง ๋  ๋ ๋ง๋ค ํด๋ฆฐ์ ํจ์๊ฐ ์คํ๋๋ ์ด์ต

---

#### useLayoutEffect ํ

useEffect() ํ๊ณผ ์ฌ์ฉ๋ฒ์ด ๋์ผํ useLayoutEffect() ใฐ
์ฐจ์ด์ ์ ์คํ๋๋ ์๊ธฐ๐
ํ์ด์ง ๋ก๋ ์ฐจ๋จ์ ๋ฐฉ์งํ๊ธฐ ์ํด DOM์ด ๋ ๋๋ง ๋ ์ดํ useEffect() ํ์ ์ค์ ๋ ์ฝ๋ฐฑํจ์๊ฐ ์คํ๋๋ฉด ์์น ๋ฐ ์คํ์ผ ์ ์ฉ์ ๋ฌธ์ ๊ฐ ๋ฐ์ํ  ์ ์๋ค. 
์ด๋ฌํ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํด์ผ ํ  ๊ฒฝ์ฐ useLayoutEffect() ํ์ ์ฌ์ฉํ๋ค.

**useLayoutEffect() ํ์ DOM์ด ๋ ๋๋ง ๋๊ณ  ํ์ธํ ๋๊ธฐ ์ง์ ์ ์คํ๋๋ค. 
๋ฐ๋ฉด, useEffect๋ DOM ํ์ธํ ์ดํ ์คํ๋๋ค.**

```jsx
useLayoutEffect(() => {
	// ์ปดํฌ๋ํธ ๋ ๋๋ง ์๋ง๋ค ์คํ
});

useLayoutEffect(() => {
	// ์ด๊ธฐ ๋ง์ดํธ ๊ณผ์  ์ดํ 1ํ ์คํ
}, []);

useLayoutEffect(() => {
	// ์์กดํ๋ ์ํ ๊ฐ์ด ์๋ฐ์ดํธ ๋  ๋ ๋ง๋ค ์คํ
}, [state]);
```

- **useEffect vs. useLayoutEffect ํ**
    
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
    

[Hooks API Reference - React useLayoutEffect ํ](https://ko.reactjs.org/docs/hooks-reference.html#uselayouteffect)



---



