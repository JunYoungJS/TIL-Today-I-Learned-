# 반복문 예시

- for in 문
  - 객체 순회 경우 key 값 출력
  - 배열 순회 경우 인덱스 값 출력
  - 일반 반복문과달리 const 사용 가능

```javascript
let a = [1, 2, 3];
let obj = {
  a: 1,
  b: 2,
  c: 3,
};
for (const i in a) {
  console.log(i); //0,1,2 인덱스출력 (배열)
}
for (const i in obj) {
  console.log(i); // a,b,c key값 출력
}
```

- for of 문
  - 반복가능한 객체를 순회한다.
    - Array Map,Set ,String,arguments
  ```javascript
  let array = [1, 2, 3];
  let obj = {
    a: 1,
    b: 2,
    c: 3,
  };
  for (const a of array) {
    console.log(a); // 1,2,3
  }
  ```

for (const a of obj) {
console.log(a); // not iterable
}

```

```
