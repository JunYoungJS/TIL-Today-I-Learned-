# 클로저 란 ?

- 내부함수가 외부함수의 지역변수를 접근할수 있는데 이때 외부함수의 실행이 끝나서 외부함수가
  소멸된 이후에도 내부함수가 외부함수의 변수에 계속 접근할수있음

```js
function outter() {
  var title = "coding everybody";
  return function () {
    alert(title);
  };
}
inner = outter();
inner();
```

- 클로저를 사용하여 private 변수를 만드는 예

```js
function factory_movie(title) {
  return {
    get_title: function () {
      return title;
    },
    set_title: function (_title) {
      title = _title;
    },
  };
}
ghost = factory_movie("Ghost in the shell");
matrix = factory_movie("Matrix");

alert(ghost.get_title());
alert(matrix.get_title());

ghost.set_title("공각기동대");
```

# 클로저 장점

- 전역변수 사용을 줄일 수있음
- 외부에 해당변수를 노출시키지않음 (정보은닉)

# 클로저 단점

- 프로그램이 종료될떄까지 클로저에 할당된 변수는 메모리에 계속 남아있음
