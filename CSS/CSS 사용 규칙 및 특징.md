# CSS 사용 규칙

```css
h1(태그값 or 클래스값 or id값) {
  속성명: 속성값;
}

태그명 h1 {
  color: red;
  font-size: 50px;
}

. 클래스명 .hello {
  color: blue;
  //속성 :value
}

id값 #hi {
  color: black;
}
```

# CSS 특징

- CasCading 위에서부터 아래 순으로 적용된다.

  > 중복되는게 있을경우 마지막에 선언된것이 적용된다.

- Block 속성

  - 요소 옆에 다른것이 오지못함 (한칸 단위)
  - div,시맨틱태그,p태그 등이 있음
  - display 속성을 통해 Inline 변경가능
  - width와 height 속성을 지정할수있음

- Inline 속성

  - 요소 옆에 다른것이 올수있음
  - span, a 태그 등이 있음
  - display 속성을 통해 Block으로 변경 가능
  - width와 height속성 지정 불가능
  - 위 아래에 margin을 가질수없음 (좌우만 가능 )
  - padding 은 적용가능

- Inline Block 속성

  - 블록요소를 인라인 속성으로 인식하게 할수있음
  - 맨 끝요소의 마진 부분이 남음 (단점)
  - 요소 사이의 간격이 조금 남음 (단점)
  - 반응형 디자인을 지원하지않음 (단점)

- id 값 (#)

  - 고유속성
  - html 문서내에 유일하게 하나의값 만 가질수 있음

  ```html
  <div id="first"></div>
  ```

- class 값 (.)
  - html 문서내에서 동일한 class 값을 여러개 가질수 있음

```html
<div class="first"></div>
<h1 class="first></h1>
```

- inherit 속성
  - 부모에 해당하는 element에게 속성을 상속받는다 .
