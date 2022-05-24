# CSS 트랜지션 속성

> 어떠한상태를 다른상태로 변화시킴

- transition-duration 속성 : 몇초동안 재생할지 정함
- transition-delay 속성 : 이벤트 발생후 몇초후에 재생할지 정함
- transition-property : 어떤속성순으로 변형할지 지정
- trasition-timing-function : 수치변형함수를 지정

- transition 속성이름(background,radius),시간(duration),타이밍함수(ease-in),딜레이 순으로 줄수도있음
- 위치,크기,박스,테두리,색상,투명도,변환 속성을 바꿀쑤있음

  ```css
  transition-duration: 2s, 5s, 10s;
  transition-delay: 0s, 2s, 5s;
  transition-property: width, background-color, border-radius;
  <!-- 위를 아래 같이 짧게 쓸수있음  -->

  transition:width 2s ease 0s,
             background-color 2s ease 2s,
             border-radius 2s ease 4s;

  ```

> 예시코드

```css
.box {
  width: 100px;
  height: 100px;
  background-color: orange;
  transition-duration: 2s;
}
.box:hover {
  width: 400px;
  height: 300px;
}
```

> 예시코드 2

```css
/* 트랜지션 property에 따른 액션을 여러개 적용할수있음  */
.box {
  width: 100px;
  height: 100px;
  background-color: orange;
  transition-duration: 2s, 5s, 10s;
  transition-delay: 0s, 2s, 5s;
  transition-property: width, background-color, border-radius;
}
```
