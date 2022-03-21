# Pseudo selector

- 태그에 id , class 값을 주지 않고 다른방법으로 해당 태그에 접근이 가능하다
- div:first-child => div태그의 첫번쨰 자식을 선택
- div:last-child => div 태그의 마지막 자식을 선택
- div:nth-child(n) => div 태그의 n번쨰 자식을 선택
- div:nth-child(even)=> div 태그의 짝수번쨰 자식선택
- div:nth-child(odd)=>div태그의 홀수번쨰 자식선택

# CSS Combinators [참조링크]: (https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Selectors)

- div 의 자식들중 span 태그를 찾아서 효과를 주는 방법

  ```css
  div span {
    color: blue;
  }
  ```

- div 의 바로 밑 자식의 span 태그에 효과를 주는 방법

```css
div > span {
  color: black;
}
```

- div 의 형제인 바로 다음 span태그에 효과를 주는 방법 (+ 인접 형제 결합자)

```css
div + span {
  color: red;
}
```

- div 의 형제들인 span 태그 (여러개 ) 에 효과를 주는방법 (~ 일반 형제 결합자 )

```css
div ~ span {
  color: blue;
}
```

<!-- # CSS attributor Selector -->
