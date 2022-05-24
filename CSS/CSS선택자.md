# CSS 선택자

- id 값 (#)

  - 고유속성
  - html 문서내에 유일하게 하나의값 만 가질수 있음

  ```html
  <div id="first"></div>
  #first{ }
  ```

- class 값 (.)
  - html 문서내에서 동일한 class 값을 여러개 가질수 있음

```html
<div class="first"></div>
<h1 class="first></h1>
.first{}
```

- inherit 속성
  - 부모에 해당하는 element에게 속성을 상속받는다 .

# Css Pseduo Selector (가상선택자)

- 태그에 id , class 값을 주지 않고 다른방법으로 해당 태그에 접근이 가능하다
- div:first-child => div태그의 첫번쨰 자식을 선택
- div:last-child => div 태그의 마지막 자식을 선택
- div:nth-child(n) => div 태그의 n번쨰 자식을 선택
- div:nth-child(even) => div 태그의 짝수번쨰 자식선택
- div:nth-child(odd) => div태그의 홀수번쨰 자식선택
- p:nth-of-type(3)=> p태그들중 3번쨰꺼

* nth-of-type => 해당 태그들 중 선택 , nth-child =>해당태그 x 전체 중

# Css Combinator

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
