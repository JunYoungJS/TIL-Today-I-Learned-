## React Project만드는 방법

    - npx create-react-app 프로젝트이름명
    - npm start

## React Project 파일 설명

    - src -> index.js 파일을 가장 먼저 실행 (npm start시)
    - index.js 내부 파일 설명
      - ReactDom.render(컴포넌트이름,렌더링시킬 dom )

# 사용자 지정 컴포넌트 만들기

> 컴포넌트명은 카멜케이스사용

- 원하는 컴포넌트 파일을 만든다 (ex registerform.js)
- 해당 컴포넌트에대한 JSX파일을 작성한다
- export default 내 보낼 컴포넌트명
- import 컴포넌트명 from 컴포넌트위치 를 하여 사용할수있다.

# JSX 란?

- html코드를 자바스크립트로 받음
- 리액트에서 UI를 표현하기위한 문법
- static/js 의 bundle.js 파일을 보면 우리가 작성한 JSX코드를 브라우저가 읽을수있게 만듬

## JSX 문법 작성 규칙

- return 시 하나의 루트 요소 만 가져야한다

```jsx
 > <div></div> <div></div>  이런식으로 작성 x
 > <div> <div></div></div>  이런식으로 작성 o
```

## JSX에서 동적 데이터 사용방법

> {변수명} 을 사용 예시

```jsx
function ExpenseItem() {
  const expenseDate = new Date(2022, 3, 1);
  const expenseTitle = "Car Insurance";
  const expenseAmount = 294.67;

  return (
    <div className="expense-item">
      <div>{expenseDate.toISOString()}</div>
      <div className="expense-item__description">
        <h2>{expenseTitle}</h2>
        <div className="expense-item__price">{expenseAmount}</div>
      </div>
    </div>
  );
}
```

## Props 속성을 사용

- props 속성을 이용하여 상위 컴포넌트에서 하위컴포넌트로 값을 보낼수있다 .
  - 상위 컴포넌트에서 하위컴포넌트에 속성값을 넣는다
  - 하위컴포넌트의 매개변수 props에서 상위컴포넌트에서 보낸값을 사용할수있다.

> APP 컴포넌트에서 하위 컴포넌트인 ExpenseItem로 보내기 코드 예시

```jsx
// 코드 예시

import ExpenseItem from "./components/Expenseitem";
import "./App.css";

function App() {
  const expenses = [
    {
      id: "e1",
      title: "Toilet Paper",
      amount: 94.12,
      date: new Date(2020, 7, 14),
    },
    { id: "e2", title: "New TV", amount: 799.49, date: new Date(2021, 2, 12) },
    {
      id: "e3",
      title: "Car Insurance",
      amount: 294.67,
      date: new Date(2021, 2, 28),
    },
    {
      id: "e4",
      title: "New Desk (Wooden)",
      amount: 450,
      date: new Date(2021, 5, 12),
    },
  ];

  return (
    <div>
      <h2>Let's get started</h2>
      <ExpenseItem
        title={expenses[0].title}
        date={expenses[0].date}
        amount={expenses[0].amount}
      ></ExpenseItem>
      <ExpenseItem
        title={expenses[1].title}
        date={expenses[1].date}
        amount={expenses[1].amount}
      ></ExpenseItem>
      <ExpenseItem
        title={expenses[2].title}
        date={expenses[2].date}
        amount={expenses[2].amount}
      ></ExpenseItem>
      <ExpenseItem
        title={expenses[3].title}
        date={expenses[3].date}
        amount={expenses[3].amount}
      ></ExpenseItem>
    </div>
  );
}

// ExpenseItem 컴포넌트

import "./Expenseitem.css";

function ExpenseItem(props) {
  return (
    <div className="expense-item">
      <div>{props.date.toISOString()}</div>
      <div className="expense-item__description">
        <h2>{props.title}</h2>
        <div className="expense-item__price">{props.amount}</div>
      </div>
    </div>
  );
}

export default ExpenseItem;
```
