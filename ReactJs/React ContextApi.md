# React Context API 란 ?

- 컴포넌트들이 많아질경우 props를 일일히 다 전달해주기가 번거로워지는데 이를 위해 사용
  > React Context API . Redux . mobx 등으로 전역상태관리 가능

> 사용예시

```jsx
// 1. createContext를 통해 value로 사용할 값들 설정
const AuthContext = React.createContext({
  isLoggedIn: false,
});

export default AuthContext;

// 2. AuthContext.Provider로 wrapping 한다 .
// wrapping된 컴포넌트들은 value값을 하위 컴포넌트에 전달할수있음
<AuthContext.Provider value={isLoggedIn}>

<MainHeader onLogout={logoutHandler} />
      <main>
        {!isLoggedIn && <Login onLogin={loginHandler} />}
        {isLoggedIn && <Home onLogout={logoutHandler} />}
      </main>
</AuthContext.Provider>;


// 3. 해당 컴포넌트에서 값을 전달받아서 사용하는방법
// 1. <AuthContext.Consumer로 전달 >
const Navigation = (props) => {
  return (
    <AuthContext.Consumer>
      {(ctx) => {
        return (
          <nav className={classes.nav}>
            <ul>
              {ctx.isLoggedIn && (
                <li>
                  <a href="/">Users</a>
                </li>
              )}
              {ctx.isLoggedIn && (
                <li>
                  <a href="/">Admin</a>
                </li>
              )}
              {ctx.isLoggedIn && (
                <li>
                  <button onClick={props.onLogout}>Logout</button>
                </li>
              )}
            </ul>
          </nav>
        );
      }}
    </AuthContext.Consumer>
  );
};

export default Navigation;

// 3.2 useContext 훅을 사용하여 값을 받을수있음
import AuthContext from "../../store/auth-context";
const Navigation = (props) => {
    const ctx=useContext(AuthContext) // AuthContext는 store
        return (
          <nav className={classes.nav}>
            <ul>
              {ctx.isLoggedIn && (
                <li>
                  <a href="/">Users</a>
                </li>
              )}
              {ctx.isLoggedIn && (
                <li>
                  <a href="/">Admin</a>
                </li>
              )}
              {ctx.isLoggedIn && (
                <li>
                  <button onClick={props.onLogout}>Logout</button>
                </li>
              )}
            </ul>
          </nav>
        );
      }}
};
```

## Context Api의 단점

- Provider 가 제공하는 value prop에 있는 state가 변할떄마다 Provider가 wrapping 하는 모든 컴포넌트들이 리렌더링

# Context Api 사용 예시 패턴

- store 폴더생성
- 컴포넌트에 사용될 값들인 cart-context.js 선언

  ```jsx
  <!-- cart-context.js -->
  import React from "react";
  const CartContext = React.createContext({
    items: [],
    totalAmount: 0,
    addItem: (item) => {},
    removeItem: (id) => {},
  });
  export default CartContext;
  ```

- 전체 컴포넌트에 제공할 cart-provider.js 선언

```jsx
import CartContext from "./cart-context";
// cart-provider.js
const CartProvider = (props) => {
  const addItemToCartHandler = (item) => {};
  const removeItemFromCartHandler = (id) => {};

  const cartContext = {
    items: [],
    totalAmount: 0,
    addItem: addItemToCartHandler,
    removeItem: removeItemFromCartHandler,
  };

  return (
    <CartContext.Provider value={cartContext}>
      {props.children}
    </CartContext.Provider>
  );
};

export default CartProvider;
```

- CartProvider의 value를 사용할 컴포넌트에 wrapping 함

```jsx
<CartProvider>
  {cartIsShown && <Cart onClose={hideCartHandler} />}
  <Header onShowCart={showCartHandler} />
  <main>
    <Meals />
  </main>
</CartProvider>
```
