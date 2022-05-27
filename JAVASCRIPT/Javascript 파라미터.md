## Javascript default 파라미터

- 매개 변수에 값이 안들어올떄 기본값으로 지정할수있음

```js
const a = (x = 1, y = 2, z = 3) => {
  console.log(x, y, z);
};

a(0);
// default parameter의 인자도 사용 가능
// 단 let과 동일하게 작동하므로 default parameter뒤에 선언된 변수는 사용 x
const b = (a = 1, b = a + 1, c = 3) => {
  console.log(a, b, c);

  const getDefault = () => {
    console.log("Default Parameter");
  };
  // 함수도 인자로 사용가능
  const c = (x, y = getDefault()) => {
    console.log(x, y);
  };

  let k = 1;

  // 같은변수명 사용 불가 x a=k여야함
  const d = (k = k, b = 1) => {
    console.log(a, b);
  };
};
```

> arguments에는 인식못함

## Javascript rest parameter (나머지)

```js
const f = (a, ...list) => {
  // 무조건 파라미터의 마지막에 써줘야함
  console.log(list); // 1,2,3,4,5
};
f(1, 2, 3, 4, 5);
```

## Javascript spread operator (얕은복사만 가능 )

- 예시

```js
const number = [1, 2, 3];
const number2 = [4, 5, 6];
const numbers = [...number, ...number2]; //1,2,3,4,5,6 => concat가능
const numbers2 = [...number2, ...number]; //4,5,6,1,2,3

// 최대값 출력
const maxValue = Math.max(...numbers); // 6
```

- iterable 한 데이터를 펼칠수있음 (set 문자열 등 )

```js
const str = "hi";
const tmp = [...str]; // => [h,i]
```

## shorthand property

```js
const a = 10;
const b = 11;
const obj = {
  a,
  b,
}; //a:10 b:11
```

## concised method

```js
const obj = {
  name:'홍길동',
  getName(){return this.name}
  getName2:function(){return this.name}
  // getName : 기존에 있었던 prototype 속성이 사라짐 (성능 개선)
  // getName2 : prototype 속성이 있음
};
```

## computed property

```js
const className = "123";
const hi = {
  ["hi" + className]: "1",
};

function name(n) {
  return `${n} : name`;
}
let obj = {
  [`key${name("홍길동")}`]: "name",
};
```
