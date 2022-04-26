# Redux란 ?

- app-wide state 또는 cross-component state 를 위한 state 관리 시스템
- 모든 컴포넌트의 state를 관리 할수 있는 시스템

## Redux 작동방식

- 하나의 중앙 데이터 저장소에 있는 데이터로 컴포넌트들을 관리할수있음
- Subscription => 스토어에 있는 데이터를 컴포넌트가 받아서 사용하는 행위
- 컴포넌트는 중앙 데이터 저장소를 직접 변경하지 못하고 reducer를 통해 데이터를 조작
  - action 을 dispatch 해서 reducer에서 state를 조작

## Local State란?

- 하나의 컴포넌트에 종속되는 state

## Cross component state 란?

- 여러개의 컴포넌트에 미치는 State => props drilling이 필요

## App-Wide State란 ?

- App 전체에 미치는 State
  - ex) 로그인에 따라 새로운 환경이 제공

## Recat Context api 단점

- 코드가 복잡해짐
- 대규모 어플리케이션에서 state관리가 복잡해짐
- state값이 변경될때마다 provider로 wrapping하여 useContext의 value를 사용하는 자식들이 모두 리렌더링된다
