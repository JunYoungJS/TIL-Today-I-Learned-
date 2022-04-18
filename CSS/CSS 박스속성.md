# CSS Box 속성

- margin

  - box의 border(경계)로부터 바깥에 있는공간
  - margin 20px : 상 하 좌우 20px
  - margin 20px 15px : 상 하 20px 좌우 15px
  - margin 20px 5px 12px 9px (위쪽 오른쪽 아래쪽 왼쪽 => 반시계방향)

- margin 겹침 현상

  - 위 아래 동일한 margin이면 둘중 하나의 마진만 반영
  - 위 아래 값이 다른 margin을 주면 둘중에 더 큰값으로 병합
  - 좌우로는 발생 x

- margin 겹침 현상 발생 2
- 부모와 자식태그 간에서도 발생 됨

  - 부모태그에 border속성이 사라진경우

- padding

  - # box의 border부터 안쪽에 있는 공간
  - box의 border로부터 안쪽에 있는 공간
    <img width="436" alt="스크린샷 2022-03-29 오후 3 44 27" src="https://user-images.githubusercontent.com/100929485/160550109-a9b0eb11-2280-4cda-a5f6-4e54cbd18b1f.png">

- border
  - 박스의 경계선
  - border은 굵기 스타일 색상 순이다
  - Inline 속성에 적용가능
