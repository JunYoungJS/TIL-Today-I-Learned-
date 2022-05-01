# Redux Toolkit 이란?

- Redux를 더 사용하기 쉽게 만들기 위해 Redux에서 제공하는 개발도구

# 기존의 Redux코드

```jsx // store.js
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

- 액션타입 명시
- 기존 state값 반환

# Redux Toolkit을 사용한 코드

```jsx
import { createSlice, configureStore } from "@reduxjs/toolkit";

const initialState = { counter: 0, showCounter: true };
const counterSlice = createSlice({
  name: "counter",
  initialState: initialState,
  reducers: {
    increment(state) {
      state.counter++;
    },
    decrement(state) {
      state.counter--;
    },
    increase(state, action) {
      state.counter = state.counter + action.payload;
    },
    toggleCounter(state) {
      state.showCounter = !state.showCounter;
    },
  },
});

const store = configureStore({
  reducer: counterSlice.reducer,
});

export const counterActions = counterSlice.actions;
// 액션 dispatch
export default store;
```

> > Redux에비해 코드량이 많이 줄어듬 ,기존 State값 반환 x

## createSlice

- name,initialstate,reducers 로 정의
- action 과 reducer를 하나의 파일에서 관리 가능

## configureStore

- store에있는 reducer를 지정할수있음

## 기존의 Redux코드를 사용한 Counter.js

```jsx

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

```

## 개선된 Redux 툴킷을 사용한 Counter js 코드

```jsx
import { counterActions } from "../store/index.js";
import { useSelector, useDispatch } from "react-redux";
import classes from "./Counter.module.css";

const Counter = () => {
  const dispatch = useDispatch();
  const counter = useSelector((state) => state.counter);
  const show = useSelector((state) => state.showCounter);

  const toggleCounterHandler = () => {
    dispatch(counterActions.toggleCounter());
  };

  const increaseHandler = () => {
    dispatch(counterActions.increase(10));
  };
  const incrementHandler = () => {
    dispatch(counterActions.increment());
  };
  const decrementHandler = () => {
    dispatch(counterActions.decrement());
  };

```
