# 웹 페이지 내에서 원하는 요소 노드에 접근하기

### 🦄 document.getElementById 혹은 Id를 사용해 요소 검색하기
요소에 id 속성이 있으면 위치에 상관없이 메서드 document.getElementById(id)를 이용해 접근할 수 있다.

```jsx
<div id="elem">
  <div id="elem-content">Element</div>
</div>

<script>
  // 요소 얻기
  let elem = document.getElementById('elem');

  // 배경색 변경하기
  elem.style.background = 'red';
</script>
```
`id` 속성 값을 그대로 딴 전역 변수를 이용해 접근할 수도 있음.

⚠️ 요소 id를 따서 만들어진 전역변수를 접근시 사용하지 말 것. 실무에선 `document.getElementById`를 사용할 것. <br/>
⚠️ id는 중복되면 안된다.

### 🦄 querySelectorAll
자식 요소 중 주어진 CSS 선택자에 대응하는 요소 모드를 반환한다.
+ 가상 클래스도 사용가능
`:hover`나 `:active` 같은 CSS 선택자의 가상 크래스도 사용할 수 있다.

### 🦄 querySelector
주어진 CSS 선택자에 대응하는 요소 중 첫 번째 요소를 반환.
`ele.quertSelectorAll(css)[0]`은 선택자에 해당하는 모든 요소를 검색해 첫번째 요소만은 반환하고, `elem.querySelector`는 해당하는 요소를 찾으면 검색을 멈춘다.

### 🦄 matches
요소 `elem` 이 주어진 CSS 선택자와 일치하는지 여부를 판단해준다.

```jsx
<a href="http://example.com/file.zip">...</a>
<a href="http://ya.ru">...</a>

<script>
  // document.body.children가 아니더라도 컬렉션이라면 이 메서드를 적용할 수 있습니다.
  for (let elem of document.body.children) {
    if (elem.matches('a[href$="zip"]')) {
      alert("주어진 CSS 선택자와 일치하는 요소: " + elem.href );
    }
  }
</script>
```

### 🦄 closest
`elem` 자기 자신을 포함하여 CSS 선택자와 일치하는 가장 가까운 조상 요소를 찾을 수 있게 도와준다. <br/>
일치하는 요소를 찾으면 검색을 중단하고 해당 요소를 반환한다.


### 🦄 getElementsBy*
태그나 클래스등일 이용해 원하는 노드를 찾아주는 메서드 <br/>
`querySelector`을 이용하는게 더 편리해서 잘 안씀. <br/>

- `elem.getElementsByTagName(tag)`
- `elem.getElementsByClassName(className)`
- `document.getElementsByName(name)`
