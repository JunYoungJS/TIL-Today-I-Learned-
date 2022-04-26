# 함수형 컴포넌트 Redux 사용방법

- npm 으로 redux패키지와 react-redux패키지를 다운 받아야함
- store 폴더생성 (리듀서와 전역컴포넌트에 사용될 값이 들어있음 )

## Redux 사용시 주의해야할점

- reducer 내에서 값을 리턴할시 기존의 값이 아니라 새로운값을 반환해야됨 (객체나 배열등)
  - 이유: 기존의state를 유지하는식으로 업데이트를 하면 버그가 발생

### store 폴더 - index.js

```jsx
import { createStore } from "redux";

const initState = { counter: 0, showCounter: true };

const counterReducer = (state = initState, action) => {
  if (action.type === "increment") {
    return {
      counter: state.counter + 1,
      showCounter: state.showCounter,
    };
  }
  if (action.type === "decrement") {
    return {
      counter: state.counter - 1,
      showCounter: state.showCounter,
    };
  }

  if (action.type === "increase") {
    return {
      counter: state.counter + action.amount,
      showCounter: state.showCounter,
    };
  }
  if ((action.type = "toggle")) {
    return {
      showCounter: !state.showCounter,
      counter: state.counter,
    };
  }

  return state;
};

const store = createStore(counterReducer);
export default store;
```

```jsx
import React from "react";
import ReactDOM from "react-dom";
import { Provider } from "react-redux";
import "./index.css";
import App from "./App";
import store from "./store/index.js";

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById("root")
);
```

- <Provider>로 store에있는 값을 사용할 컴포넌트를 wrapping
- react-redux의 Provider와 store를 가져옴

```jsx
// store를 사용하는 컴포넌트
import { useSelector, useDispatch } from "react-redux";
import classes from "./Counter.module.css";

const Counter = () => {
  const dispatch = useDispatch();
  const counter = useSelector((state) => state.counter);
  const show = useSelector((state) => state.showCounter);
  const toggleCounterHandler = () => {
    dispatch({ type: "toggle" });
  };

  const increaseHandler = () => {
    dispatch({ type: "increase", amount: 5 });
  };
  const incrementHandler = () => {
    dispatch({ type: "increment" });
  };
  const decrementHandler = () => {
    dispatch({ type: "decrement" });
  };
  return (
    <main className={classes.counter}>
      <h1>Redux Counter</h1>
      {show && <div className={classes.value}>{counter}</div>}
      <div>
        <button onClick={incrementHandler}>Increment</button>

        <button onClick={increaseHandler}>Increase by 5</button>
        <button onClick={decrementHandler}>Decrement</button>
      </div>
      <button onClick={toggleCounterHandler}>Toggle Counter</button>
    </main>
  );
};

export default Counter;
```

- store값을 사용하고 리듀서로 액션을 보내기 위해 스토어에있는 값을 사용할 컴포넌트에서
  usedispatch(액션보냄) useSelector(스토어에있는 값을 사용 )

# Redux에서 사용하는 것들

## useDispatch

- store의 리듀서에 사용될 액션을 dispatch함
- dispatch('액션타입',patch할 action값)

## useSelector

- 리덕스의 store에 있는 state값을 조회할수있음
