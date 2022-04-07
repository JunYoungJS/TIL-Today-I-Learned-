## useReducer

- useState와 비슷하나 좀더 복잡한 로직과 상태관리에서 사용
- const [상태객체,distpatch함수]=useReducer(리듀서함수,초기상태,초기함수) 로사용
  > 예시

```jsx
const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({ type: "decrement" })}>-</button>
      <button onClick={() => dispatch({ type: "increment" })}>+</button>
    </>
  );
}
```

- useReducer(리듀서 함수, 초기상태값 지정) , state는 상태값으로 사용할수있는 변수 dispatch로 리듀서로 등록된 함수(reducer)에 보낼수있음
- reducer 함수의 인자로 state와 action 이있는데 여기서 state는 현재 상태값이고 action 은 dispatch함수에 전달된 값
