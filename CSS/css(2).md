# CSS 속성 (2)

## Flex

- 자식 엘리먼트에 말하지 않고 부모 엘리먼트에게만 말한다.
- justify-content(수평방향) 속성을 통해 위치를 지정할수있음
- align-items(수직방향) 속성을 통해 위치를 지정할수있음
- align-items가 동작하지않을 경우 부모엘리먼트에 높이 100vh를 준다
- flex-direction 속성을 통해 수평방향 과 수직방향의 축을 바꿀수있다.
- flex-wrap 속성을 통해 wrap을 설정하면 한 줄에 컨텐츠가 들어갈수있는만큼 보여줌
- position 속성
- align-self : 한요소만 옮길떄 사용하는 방식
- align-content : 열 사이의 공간을 조절한다. (단일행 단일열 적용 x)

[Flex연습](https://flexboxfroggy.com/#ko)

## Fixed

- position 속성
- 다른 레이어상에 자리를 잡을수있다.
- 가장 위에 위치하게 된다.
- 스크롤을 해도 항상 그자리에 머문다. (고정된위치)

## Position Relative

- 처음 생성된 위치를 기준으로 두고 상하좌우 움직일수 있음

## Position absoulte

- 가장 가까운 relative 부모를 기준으로 움직일수있게 만듬
