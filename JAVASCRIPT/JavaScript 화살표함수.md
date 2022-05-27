# 화살표 함수

```javascript
var a = function () {
  return new Date();
};

var a = () => {
  return new Date();
};
var a = () => new Date();

var b = function (a) {
  return a * a;
};
var b = (a) => a * a;

var c = function (x) {
  return {
    x: x,
  };
};

// return 값이 객체일경우 ()붙여야함
var c = (x) => ({
  x: x,
});
```

## 화살표함수 특징

- this바인딩을 하지 않고 상위스코프의 this를 잡음
- 생성자함수를 만들수 없음 (프로토타입 프로퍼티 존재 x)
- call,bind,apply 메소드를 써도 this바인딩을 할수는없지만 함수 본래기능은 수행가능
