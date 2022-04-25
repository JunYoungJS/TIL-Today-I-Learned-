# Redux란 ?

- app-wide state 또는 cross-component state 를 위한 state 관리 시스템
- 모든 컴포넌트의 state를 관리 할수 있는 시스템

## Local State란?

- 하나의 컴포넌트에 종속되는 state

## Cross component state 란?

- 여러개의 컴포넌트에 미치는 State => props drilling이 필요

## App-Wide State란 ?

- App 전체에 미치는 State
  - ex) 로그인에 따라 새로운 환경이 제공

# Redux vs React Context api

## Recat Context api 단점

- 코드가 복잡해짐
- 대규모 어플리케이션에서 state관리가 복잡해짐
- state값이 변경될때마다 provider로 wrapping하여 useContext의 value를 사용하는 자식들이 모두 리렌더링된다
