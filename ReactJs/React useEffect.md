## Side Effect 란 ?

- 어플리케이션에서 발생할수 있는 모든 일들
  - https 리퀘스트를 보내서 브라우저 스토리지에 무언가를 저장 (데이터가져오기)
  - 수동으로 Dom 수정하기
  - 타이머나 인터벌 함수 작동등
    > Side Effect를 다루기 위해서 useEffect를 사용

## useEffect

```jsx
//  1. 컴포넌트 실행시 맨처음에만 실행
useEffect(() => {}, []);

// 2.  color 변수가 변경될시 실행
useEffect(() => {
  console.log("color changed");
}, [color]);

// 3. 클린업
useEffect(() => {
  console.log("color changed");

  return () => {
    //code  컴포넌트가 해제되기 전에 실행됨
  };
}, [color]);
```


