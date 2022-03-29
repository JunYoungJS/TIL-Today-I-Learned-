# HTML 파일에 CSS 넣는방법

- head 태그 안에 style태그를 정의하고 style태그 내부에 css 값들을 넣는다

```html
<head>
  <style>
    h1 {
      color: blue;
    }
  </style>
</head>
```

- head 태그 안에 link stylesheet=css로 선언하고 css파일을 만들어서 link태그와 연결한다 (css파일 분리)

```html
<link href="css파일명" rel="stylesheet/>

```

### 두번째 방법을 선호

<br>

# CSS 사용 규칙

```css
h1(태그값 or 클래스값 or id값) {
  속성명: 속성값;
}

태그값 h1 {
  color: red;
  font-size: 50px;
}

클래스값 .hello {
  color: blue;
}

id값 #hi {
  color: black;
}
```

# CSS 특징

- 위에서부터 아래로 적용된다.

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

# CSS Box 속성

- margin

  - box의 border(경계)로부터 바깥에 있는공간
  - margin 20px : 상 하 좌우 20px
  - margin 20px 15px : 상 하 20px 좌우 15px
  - margin 20px 5px 12px 9px (위쪽 오른쪽 아래쪽 왼쪽 => 반시계방향)

&nbsp;

- padding
  <<<<<<< HEAD
  - # box의 border부터 안쪽에 있는 공간
  - box의 border로부터 안쪽에 있는 공간
    <img width="436" alt="스크린샷 2022-03-29 오후 3 44 27" src="https://user-images.githubusercontent.com/100929485/160550109-a9b0eb11-2280-4cda-a5f6-4e54cbd18b1f.png">

> > > > > > > 5ee6f79afce9ee42b2b3c0fd8bd5c0004a831a3d

&nbsp;

- border
  - 박스의 경계선
  - border은 굵기 스타일 색상 순이다

&nbsp;

- margin 충돌현상

  - 상위박스와 하위박스의 경계가 같으면 margin이 바뀌지않음
  - 하나가 된다
  - 위 아래에서만 발생

# CSS 규격단위

- Relative (상대단위)

  - em
    - 1em = 부모 요소와 같은 크기 , 2em = 부모 요소보다 2배 큰 크기
    - 즉 부모요소에 따라 상대적으로 크기가 변환됨
    - 부모의요소가 중첩 되어 예상하지 못한 크기가 나올수있음
  - rem
    - 글꼴 크기를 부모요소 크기에 바꾸지않고 루트 html요소에 따라 바뀜
  - vh
  - vw
  - %
    - (너비와 높이는 부모의 요소를 기준으로)

- Absoulte (절대단위)
  - px
  - pt
  - cm
  - in
  - mm

# CSS 우선순위

- 1.  인라인스타일 , !important (둘다 안쓰는걸 추천 )
- 2.  id선택자 : 100
- 3.  class선택자 : 10
- 4.  요소와 가상요소 선택자 :1

```css
section p {
  // 요소 2개  / 0 0 2
}

#submit {
  // id 선택자 1개 / 1 0 0
}

nav a.active {
  // 클래스 1개  요소 2개  0 1 2
}
```

> 숫자가 클수록 우선순위가 높아짐
