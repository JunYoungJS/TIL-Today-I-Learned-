# this 란 ?

- 메소드 or 일반함수 or 이벤트리스너 를 호출한 객체가 저장되어있는 속성

예시코드

```javascript
var value = 0;
var obj = {
  value: 1,
  setvalue: function () {
    this.value = 2(
      //obj.value
      function () {
        this.value = 3;
      }
    )(); //즉시 실행함수 => window
  },
};
obj.setvalue(); // this = obj
console.log(value); // 3
console.log(obj.value); // 2
```

- call,bind,apply 를 통해 this를 지정할수있음

## 화살표 함수에서의 this

- 상위스코프의 this를 가리킨다. (this바인딩 x)
- 함수스코프를 생성하되 실행컨텍스트 생성시 (this 바인딩 x)

```javascript
const obj = {
  a() {
    console.log(this);
    const b = () => {
      console.log(this); // 상위스코프의 this =>  obj
    };
    b();
  },
};
obj.a();
```

```javascript
const person = {
  name: "Lee",
  sayHi: () => console.log(`Hi ${this.name}`), // 상위스코프의 this 출력 => window.name== undefined
};

person.sayHi();
```

- 프로토타입도 마찬가지로 this 바인딩 x

```javascript
const person = {
  name: "Lee",
};

Object.prototype.sayHi = () => console.log(`Hi ${this.name}`);

person.sayHi(); // Hi undefined
```

- 화살표함수는 prototype 프로퍼티를 가지고 있지 않아 생성자함수로 사용불가

```javascript
const Foo = () => {};

// 화살표 함수는 prototype 프로퍼티가 없다
console.log(Foo.hasOwnProperty("prototype")); // false

const foo = new Foo(); // TypeError: Foo is not a constructor
```

- 콜백함수의 this => window 를 가리킴

```javascript
var button = document.getElementById("myButton");
button.addEventListener("click", () => {
  console.log(this === window); // => true
  this.innerHTML = "Clicked button";
});
```


