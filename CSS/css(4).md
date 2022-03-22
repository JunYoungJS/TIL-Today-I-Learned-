# CSS 애니메이션 속성

## transition 속성

- 어떤상태에서 다른상태로 변화를 보내주는 애니메이션 (hover, active focus)
- transition의 속성은 원래 root에 넣는다 (state가없는속성)
- ease-in funtion (브라우저에게 변화하는 방법을 알려준다.)
  - linear (직선)
  - ease-in (시작과 끝이 빠름)
  - ease-out (시작과 끝이 느림)
  - ease-in-out (시작이 빠르고 끝이 느림)
  - all (변화요소를 한번에 다룸 )
  - cubic-beizer() 로 직접 설정이가능

> 예시

```css
a {
  color: red;
  trasition: all(바꿀속성 background-color등) 5s ease-in-out;
}
a:hover {
  color: white;
}
```

## transform 속성

- 하나의 요소를 변경시킨다.
- transform : rotateY(50deg) rotateX(20deg) 등이 있다
- box Element 요소를 변형시키지 않음 (형제들에게 영향 x)
- margin padding 이 적용 되지 x
- 페이지의 픽셀의 다른 부분에서 발생

## 애니메이션 만들기

```css
@keyframe 애니메이션이름 {
  from {
      효과
  }
  to {
      효과
  }
}

img{
    animation: 애니메이션이름 속성값
}
```

> 애니메이션 예시

```css
@keyframe hello {
  from {
    transform: rotateX(0);
  }
  to {
    transform: rotateY(360deg);
  }
}

img {
  animation: hello 5s ease-in-out infinite;
}
```

```css
@keyframe hello1 {
  0% {
    transform: rotateX(0);
  }
  ,
  25% {
    transform: rotateY(0);
  }
  ,
  50% {
    transform: rotateX(30);
  }
  ,
  75% {
    transform: rotateX(60);
  }
}
```
