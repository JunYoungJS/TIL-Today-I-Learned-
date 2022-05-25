# CSS 애니메이션 속성

- 트랜지션 속성을 애니메이션 보다 많이사용 , 트랜지션으로 구현이가능하면 트랜지션을 사용하는것을 추천
- 트랜지션과 애니메이션을 결합해 사용도함

# 애니메이션 속성

## animation-name 속성

- 사용할 사용할 애니메이션 이름을 지정 keyframes name(애니메이션 이름)

## animation-direction 속성

- 애니메이션의 진행 방향을 설정
  - alternate : from에서 to로 이동후 to에서 from으로 다시이동
  - normal : 계속 from에서 to로 이동

## animation-duration 속성

- 애니메이션을 몇초동안 재생할지 지정

## animation-iteration-count 속성

- 애니메이션 반복횟수를 지정
  - infinite

## animation-play-state

- 애니메이션의 재생상태를 지정

> 사용 예시

```css
#box {
  position: absolute;
  width: 200px;
  height: 200px;
  border-radius: 100px;
  text-align: center;
  background: linear-gradient(#cb60b3 0%, #db36a4 100%);

  animation-name: rint;
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
  animation-timing-function: linear;
}
#box > h1 {
  line-height: 200px;
}
/* 애니메이션 지정  */
@keyframes rint {
  from {
    //0%
    left: 0;
    transform: rotate(0deg);
  }
  50% {
    left: 500px;
  }
  to {
    //100%
    left: 500px;
    transform: rotate(360deg);
  }
}
```

- animation : 키프레임명(애니메이션지정),지속시간,timingfunction,delay,iteration count,direction
