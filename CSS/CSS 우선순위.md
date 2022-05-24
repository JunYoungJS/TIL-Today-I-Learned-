# CSS 우선순위

- CasCading이므로 위에서부터 아래 순으로 적용된다. (가장 나중에 선언된게 적용됨)

  > 중복되는게 있을경우 마지막에 선언된것이 적용된다.

- 1순위 : !important로 선언된것
- 2순위 : 인라인스타일로 적용된것 (html 파일에서 style로 선언)
- 3순위 : id속성
- 4순위 : class,attribute,pseudo-class 속성
- 5순위 : tag name
- 6순위 : 부모 요소에 의해 상속
