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
