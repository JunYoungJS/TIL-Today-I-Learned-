# Object (객체)

- name과 value 로 구성된 프로퍼티의 정렬되지 않은 집합
- 프로퍼티로 함수가 올수있음 (메소드)
- 원시형 타입을 제외 한 함수, 배열, 정규표현식등이 해당
- mutable한 value이다

- Computed Property

  - 표현식을 이용해 객체의 key값을 정의하는 문법

  ```js
  let a = "age";
  const user = {
    name: "Mike",
    [a]: 30,
  };
  ,
  let user={
      [1+4]:5
  }
  ```

- Object.assign()

  - 객체를 복제

  ```js
  const user = {
    name: "man",
    age: 30,
  };
  const cloneUser = user; // 동일한 주소를 가리키게 되므로 clone user를 가질수가없음
  const cloneUser = Object.assign({}, user); // 를 통해 객체를 복제할수있음
  ```

# Symobol 형

- 유일한 식별자를 만들때 사용 (유일성보장)
