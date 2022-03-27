# CSS PSEUDO Classes

- active : 대상을 클릭할때 발생
- hover : 마우스가 대상 위에 있을떄 발생
- focus : 키보드로 선택되었을시 발생
- visited : 링크에 방문 했을시 발생 (a 태그에서 사용 )
  > 사용방법 예시

```css
button:active {
  color: blue;
}
button:hover {
  background-color: yellow;
}
a:visited {
  background-color: white;
}
```

- 다른 엘리먼트와 연계해서 사용하는 예시

  ```css
  form:hover input {
    // form에 올려져있을시 input 태그의 배경색을 빨강색으로 만듬
    background-color: red;
  }

  form:hover input:focus {
    //form에 올려져있고 input태그에 focus되어있을시
  }
  ```

# Pseudo Element [참고링크](https://www.w3schools.com/css/css_pseudo_elements.asp)

- :: placeholder (placeholder 꾸밀떄)
- :: selection (드래그 했을떄)
- :: first-line 첫줄
- :: first-letter 첫글자

# Pseudo selector

- 태그에 id , class 값을 주지 않고 다른방법으로 해당 태그에 접근이 가능하다
- div:first-child => div태그의 첫번쨰 자식을 선택
- div:last-child => div 태그의 마지막 자식을 선택
- div:nth-child(n) => div 태그의 n번쨰 자식을 선택
- div:nth-child(even)=> div 태그의 짝수번쨰 자식선택
- div:nth-child(odd)=>div태그의 홀수번쨰 자식선택

# CSS Combinators [참조링크]: (https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Selectors)

- 자손 선택자 (Descendent Combinator) : div 의 자식들중 span 태그를 찾아서 효과를 주는 방법

  ```html
  <div>
    <span></span>
    <span></span>
    <h1></h1>
  </div>

  div span { color: blue; }
  ```

- 직계 자손 선택자 (>) div 의 바로 밑 자식의 span 태그에 효과를 주는 방법

```html
<div>
  <span> </span>
</div>

div > span { color: black; }
```

- 인접 형제 선택자 (+) : div 의 형제인 바로 다음 span태그에 효과를 주는 방법

```html
<div></div>
<span> </span>
div + span { color: red; }
```

- 일반 형제 선택자 ( ~) : div 의 형제들인 span 태그 (여러개 ) 에 효과를 주는방법

```html
<div></div>
<span></span>
<span></span>
<span></span>

div ~ span { color: blue; }
```

# CSS attribute Selector [참고링크](https://developer.mozilla.org/ko/docs/Web/CSS/Attribute_selectors)

- input[type="text"]{} => 타입이 text인 input 만을 선택
- input[type~="text"]{} => text를 포함하는 input 선택
- input[type$="word"]{} => 끝에 word가 오는 input 선택
- input[type^="word"]{} => 앞에 word가 오는 input 선택

# Css에서 사용되는 변수 (Custom Property)

- 1.  :root라는 엘리트먼트에 변수 추가 (root는 모든 document의 뿌리 )
- 2.  --main-color (변수명)

```css
:root {
  --main-color: red;
}

p {
  background-color: var(--main-color);
}
```

> 사용예시

# [참고링크](https://developer.mozilla.org/ko/docs/Web/CSS/Using_CSS_custom_properties)
