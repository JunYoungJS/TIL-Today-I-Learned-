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
