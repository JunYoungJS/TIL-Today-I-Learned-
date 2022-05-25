# CSS 추가규칙

> @-rule 로 표현

## @import 규칙

- css 파일을 불러올떄 사용
- link 태그를 대신해서도 사용
  - @import url("1.css")

## @font-face 규칙

- 웹 폰트를 생성할떄 사용하는 규칙

```css
@font-face {
  font-family: "font name";
  src: url("/content/file.eot") local("폰트명") // 로컬에있는 폰트이름
    url("폰트파일명") // 외부에있는 폰트를지정
;
}
* {
  font-family: "font-face에서 지정한 font-family명";
}
```

## @media 규칙

- 기기에 따른 반응형웹을 만들수있음
- @media screen 데스크탑화면에서 사용
- @media print 프린트화면에서 사용

* 주의사항 : 반응형웹에 사용하는 meth태그를 head안에 명시해야됨

> 예시코드

```css
/* 최대 너비가 767인화면까지 해당 스타일 적용  */
@media screen and (max-width: 767px) {
}

/* 최소너비 767~ 959까지 해당스타일 적용  */
@media screen and (min-width: 768px) and (max-width: 959px) {
}

/* 핸드폰 (가로) 화면이 수직일때 사용  */
@media screen and (orientation: portrait) {
}

/* 핸드폰 (세로) 화면이 수평일떄 사용  */
@media screen and (orientation: landscape) {
}
```
