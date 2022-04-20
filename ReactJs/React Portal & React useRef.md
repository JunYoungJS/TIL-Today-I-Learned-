## React Frament 란 ?

- DOM에 의미 없는 div를 사용하지 않고 여러 하위노드들을 그룹화해서 사용할수있다.
- DOM에 의미 없는 div를 사용하지 않아 성능이 좋아진다. => dom에 추가 x
- <React.Fragment> or <> 빈태그로 사용 (빈태그로 사용시 key값 설정 못함 )

## React Portal 이란?

- DOM에서 원하는 위치에 컴포넌트를 배치 시킬수 있음

  > modal 창을 만들떄 사용함

- ReactDOM.createPortal(this.props.children,document.body);
  - 첫번째인자는 컴포넌트 , 두번쨰는 위치시킬곳

## React useRef 란?

- ref라는 props를 Dom노드에 줘서 해당 엘리먼트에 쉽게 접근이가능
- useRef로 관리하는 값은 바껴도 리렌더링이 되지않는 장점이 있음

  > dom 노드에 접근할떄 추천하는 방식은 x

- 사용예시

```jsx
const userNameRef = useRef("");

<input id="username" type="text" ref={userNameRef} />;

const enteredName = userNameRef.current.value;
// >>input 태그의 value에 접근가능
```

## React forwardRef 란?

- ref props는 html의 노드에 바로 적용이되지만 html 노드가 아닌 원하는 컴포넌트 에서 ref 속성을 사용할때 사용됨
- 사용예시 (Input 컴포넌트에서 ref속성 사용 하기 )

```jsx
const MealItemForm = (props) => {
  const amountInputRef = useRef();
  return (
    <form className={classes.form} onSubmit={submitHandler}>
      <Input
        // 1. Input 컴포넌트에 ref속성 전달 (use ref사용 )
        ref={amountInputRef}
        label="Amount"
        input={{
          id: "amount_" + props.id,
          type: "number",
          min: "1",
          max: "5",
          step: "1",
          defaultValue: "1",
        }}
      />
    </form>
  );

  // 2. InPut 컴포넌트에서 forwardRef을 사용하여 ref props전달받고 원하는 태그에 ref속성을 준다.
  const Input = React.forwardRef((props, ref) => {
    return (
      <div className={classes.input}>
        <label htmlFor={props.input.id}>{props.label}</label>
        <input ref={ref} {...props.input} />
      </div>
    );
  });

  // 3. amountInputRef.current.value를 통해 컴포넌트에 ref속성을 준곳에 접근가능
  const MealItemForm = (props) => {
  const amountInputRef = useRef();
  return (
    <form className={classes.form} onSubmit={submitHandler}>
      <Input
        // 1. Input 컴포넌트에 ref속성 전달 (use ref사용 )
        ref={amountInputRef}
        label="Amount"
        input={{
          id: "amount_" + props.id,
          type: "number",
          min: "1",
          max: "5",
          step: "1",
          defaultValue: "1",
        }}
      />
    </form>
  );
};
```

# 제어 컴포넌트와 비제어 컴포넌트

## 제어 컴포넌트

- state을 통해 컴포넌트들을 제어한다
- 사용자가 입력할떄마다 state가 동기화 됨 (실시간으로 값이 반영)
  > 항상 최신값으로 유지하려는 특성 , 유효성검사할떄 주로 사용
- 사용자 입력할떄마다 리렌더링이 발생하므로 자원낭비가 심한 단점

## 비제어 컴포넌트

- ref를 통해 form element 를 제어 한다
- 리렌더링이 발생하지 않고 최종적인값으로 input value에 접근
