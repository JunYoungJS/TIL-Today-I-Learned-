# React state가 필요한이유?

- 사용자와 상호 작용이 가능한 애플리케이션을 만들수있음
- 사용자들이 클릭하고 입력하는 데이터 반응을 할수있음

```jsx
const ExpenseItem = (props) => {
  title = props.title;
  const clickHandler = () => {
    title = "hello";
    console.log("clicked!");
  };

  return (
    <Card className="expense-item">
      <ExpenseDate date={props.date} />
      <div className="expense-item__description">
        <h2>{title}</h2>
        <div className="expense-item__price">{props.amount}</div>
      </div>
      <button onClick={clickHandler}>Change Title</button>
    </Card>
  );
};
```

> onClick 이벤트를 통해 함수가 실행되면 title값이 바꾸게 유도했지만 실제로는 변경되지않음

- 리액트는 렌더링을 할때 초기에 다 렌더링을 마쳐놓은상태
- 예제 대로 할경우 react는 값이 update가 된 State인지 알수없음 => 렌더링 x
- 단순히 변수 변경만으로 리액트는 상태변화를 감지하지 못함

> 위 예제를 보안한 예시

```jsx
import React, { useState } from "react";
import ExpenseDate from "./ExpenseDate";
import Card from "../UI/Card";
import "./Expenseitem.css";

const ExpenseItem = (props) => {
  const [title, setTitle] = useState(props.title); //1. 현재 상태값 , 2 상태값을 업데이트하는요소

  const clickHandler = () => {
    setTitle("update");
    console.log("clicked!");
  };

  return (
    <Card className="expense-item">
      <ExpenseDate date={props.date} />
      <div className="expense-item__description">
        <h2>{title}</h2>
        <div className="expense-item__price">{props.amount}</div>
      </div>
      <button onClick={clickHandler}>Change Title</button>
    </Card>
  );
};

export default ExpenseItem;
```

> useState() 를 사용하여 리액트에게 컴포넌트가 업데이트가 됬다는 것을 알려 리렌더링이되게함

## useState()

- useState()의 리턴값은 1. 현재상태값 2.상태값을 업데이트하는 함수반환
- 해당 컴포넌트의 상태 변경을 가능하게함
- 컴포넌트의 개별 인스턴스 기반로 단위로 가짐 (동일한 컴포넌트가 4개있어도 그중 하나의 컴포넌트에서 상태가 바뀔시 다른 컴포넌트요소에는 영향을 안미침)

## 여러개 useState() 사용 예시

```jsx
const [enteredTitle, setEnteredTitle] = useState("");
const [enteredAmount, setEnteredAmount] = useState("");
const [enteredDate, setEnteredDate] = useState("");

const titleChangeHandler = (event) => {
  setEnteredTitle(event.target.value);
};

const amountChangeHandler = (event) => {
  setEnteredAmount(event.target.value);
};
const dateChangeHandler = (event) => {
  setEnteredDate(event.target.value);
};
```

```jsx
// 하나의 useState만으로 여러개 useState커버
const [userInput, setUserInput] = useState({
  enteredTitle: "",
  enteredAmount: "",
  enteredDate: "",
});

const titleChangeHandler = (event) => {
  setUserInput((prevState) => {
    return { ...prevState, enteredTitle: event.target.value };
  });
};

const amountChangeHandler = (event) => {
  setUserInput((prevState) => {
    return { ...prevState, enteredAmount: event.target.value };
  });
};
```
