# JavaScript 프로토타입

## 생성자 함수

    - 객체를 생성하는 함수 (constructor)

```javascript
function Person(name, gender) {
  this.name = name;
  this.gender = gender;
  this.sayHello = function () {
    alert(this.name + ' said "hello"');
  };
}
var zero = new Person("Zero", "m");
```

- 같은 생성자로부터 만들어진 객체들은 원형객체를 공유할수있는 속성 => prototype

  - 프로토타입을 이용하여 상속을 흉내낼수있음
  - 자바스크립트 객체의 부모속성

- 객체를 확장하고 객체지향적인 프로그래밍을 할수있게 해줌
- 객체를 생성할때 프로토타입이 정해짐
- 객체의 instance의 \_ _proto_ \_ 속성이나 Object.getPrototypeOf(instance명)으로 상위객체에 접근 ([[Prototype]] 으로 접근 x)
