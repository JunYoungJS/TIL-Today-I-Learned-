# HTML 파일에 CSS 넣는방법

- head 태그 안에 style태그를 정의하여 style태그 내부에 css를 넣는방법
  - ```html
    <head>
      <style>
        h1 {
          color: blue;
        }
      </style>
    </head>
    ```
- head 태그 안에 link stylesheet=css로 선언하고 css파일을 만들어서 link태그와 연결 (css파일 분리) 가장 많이 사용하는방식

  - ```html
    <link href="css파일명" rel="stylesheet/>
    ```

- 각 태그에 style 속성을 주고 style 속성 안에서 css 속성을 정의 (인라인 스타일)
  - ```html
    <h1 style="color:red"></h1>
    ```
