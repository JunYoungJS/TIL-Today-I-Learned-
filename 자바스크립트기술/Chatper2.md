# Chapter2

- Es6부터 map,set,weakmap,객체,배열을 사용할수있음
- 배열과 문자열내에 이터러블객체가 들어있어 순회가가능
- Object.entries를 통해 key value를 추출할수있음
- 기존에는 indexOf메소드를 이용하여 배열내의 값을 찾았으나 includes 메소드가 도입됨으로 인해 true false를 반환하여 쉽게 처리가 가능해짐 (indexOf 대신 includes 메소드를 이용하라)
- 원본배열이 조작되는것을 최소화시켜야함

## Spread Operator (...)

- 원하는 배열을 기존의 배열의 상태변화 없이 새로운 형태의 배열로 만들수있음
- [...items,...item] => items.concat(item) 배열을 합친다
- 리덕스 사용시 새로운 형태의 배열의 아닌 기존의 배열을 수정하는 방식으로 한다면 virtual dom은 기존의 상태변화를 감지하지 못하는 버그가 발생하므로 Spread Operator를 사용
