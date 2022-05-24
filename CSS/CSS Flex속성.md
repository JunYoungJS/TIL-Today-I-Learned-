## Flex

- Inline Box 대체
- 자식 엘리먼트에 말하지 않고 부모 엘리먼트에게만 속성을 준다 (중요!)
- justify-content(수평방향 정렬 -> 기본 , 주축 ) 속성을 통해 위치를 지정할수있음

  - flex-start : 플렉스 컨테이너의 앞쪽부터 정렬
  - flex-end : 플렉스 컨테이너의 뒤쪽부터 정렬
  - space-between : 플렉스 요소들 사이의 여유 공간을 두고 배치
  - space-around : 플렉스 요소는 앞 ,뒤 그리고 요소들 사이의 모든 여유공간을 배치

- align-items(수직방향 정렬 -> 기본 , 교차축 ) 속성을 통해 위치를 지정할수있음
- align-items가 동작하지않을 경우 부모엘리먼트에 높이 100vh를 준다

- flex-direction 속성을 통해 수평방향 과 수직방향의 축을 바꿀수있다.
- flex-wrap 속성을 통해 wrap을 설정하면 한 줄에 컨텐츠가 들어갈수있는만큼 보여줌
- position 속성
- align-self : 한요소만 옮길떄 사용하는 방식
- align-content : 열 사이의 공간을 조절한다. (단일행 단일열 적용 x)

[Flex연습](https://flexboxfroggy.com/#ko)
