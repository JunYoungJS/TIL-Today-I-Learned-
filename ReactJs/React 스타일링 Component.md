## 동적으로 인라인 스타일 적용하는 예시

```jsx
<label style={{ color: !isValid ? "red" : "black" }}>Course Goal</label>
        <input
          style={{
            borderColor: !isValid ? "red" : "#ccc",
            background: !isValid ? "salmon" : "transparent",
          }}
          type="text"
          onChange={goalInputChangeHandler}
        />

```

> style={{속성: 삼항연산자 수식 }}

## 클래스이름에 따른 스타일 적용하기

```jsx
<div className={`form-control ${!isValid ? "invalid" : ""}`}>
```

> className에 삼항연산자 조건식을 사용하여 스타일을 적용할수있음

# Styled Component

- 특정 스타일이 첨부된 컴포넌트를 빌드하는 것을 도와줌
- 스타일이 첨부된 컴포넌트에만 영향주고 다른 컴포넌트에는 영향을 주지않음
  > styled component 적용된 코드예시

```jsx
import styled from "styled-components";

const Button = styled.button`
  font: inherit;
  padding: 0.5rem 1.5rem;
  border: 1px solid #8b005d;
  color: white;
  background: #8b005d;
  box-shadow: 0 0 4px rgba(0, 0, 0, 0.26);
  cursor: pointer;

  &:focus {
    outline: none;
  }

  &:hover,
  &:active {
    background: #ac0e77;
    border-color: #ac0e77;
    box-shadow: 0 0 8px rgba(0, 0, 0, 0.26);
  }
`;
```

- Styled Components 안에 동적 props 설정

```jsx
& label {
    font-weight: bold;
    display: block;
    margin-bottom: 0.5rem;
    color: ${(props) => (props.invalid ? "red" : "black")};
  }

  & input {
    display: block;
    width: 100%;
    border: 1px solid ${(props) => (props.invalid ? "red" : "#ccc")};
    background: ${(props) => (props.invalid ? "#ffd7d7" : "transparent")};
    font: inherit;
    line-height: 1.5rem;
    padding: 0 0.25rem;
  }

<form onSubmit={formSubmitHandler}>
  <FormControl invalid={!isValid}>
    <label>Course Goal</label>
    <input type="text" onChange={goalInputChangeHandler} />
  </FormControl>
  <Button type="submit">Add Goal</Button>
</form>
```

- 1. FormControl이라는 styled component에 invalid 라는 props를 설정함
- 2. FormControl 안에있는 태그의 속성값에 props를 가져와서 조건부렌더링가능

## CSS 모듈 사용

```jsx
import styles from "./Button.module.css";
const Button = (props) => {
  return (
    <button type={props.type} className={styles.button} onClick={props.onClick}>
      {props.children}
    </button>
  );
};
```

- 파일명은 .module.css로 정해야함
- className에 styles.클래스명을 줌
