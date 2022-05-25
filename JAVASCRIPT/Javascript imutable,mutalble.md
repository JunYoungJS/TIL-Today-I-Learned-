# Javascript imutable,mutable

- Immutable 이란?

  - 불변성 , 즉 변하지않는다는것이다
  - 자바스크립트의 원시객체가 이에 속해있다.
    - Boolean ,String ,Number, Null, undefined ,Symbol
      - 재할당시 기존에 저장된 값이 바뀜

- Mutable 이란?

  - 변할수있는 값이다.
  - 자바스크립트의 일반객체들이 속해있음 (Object)

- Mutable 예시

```javascript
let x = ["foo"]; // 주소 :10
let y = x; // y= 주소 10 (x의 메모리주소를 가지고있음)

x.push("bar");

console.log(y); // ['foo', 'bar']
console.log(x === y); // true
```

- Mutable한 객체를 복사 시키는 방법

  - spread operator 나 object.assign으로 복사는 가능하나 object안에 또 object가 존재하는경우 deepcopy는 불가능함 (얕은복사만가능 depth가 1단계)
    - 재귀함수를 사용하여 프로퍼티 안의 object를 순회하면서 freeze메소드로 얼려야함

- 소스코드 예시

```javascript
var a = {
  a: 1,
  b: [1, 2, 3], // => freeze로 얼려야됨
};
```

# Object 저장 방식 (mutable)

```js
const obj = {
  a: 1,
  b: 2,
};
// obj.a=3 // const 여도 변경가능 , 왜 ? 주소 10번쨰의값을 변경시키는것이 아님

// 10 : obj -> 20
// 20 : {a,b}
```
