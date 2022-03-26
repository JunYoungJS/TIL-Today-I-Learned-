# HTML 태그에 대해 공부

## Input 태그

- 웹기반의 양식에서 사용자의 데이터를 받을수있는 대화형 컨트롤
- Input type : button, color,date ... 등 많음

```html
<input type="color" />
```

- Input 속성 : autofocus(자동초점) , disable(잠금) , minlength(최소길이지정) , placeholder(양식컨트롤이 비어있을떄사용) , required (값 입력을 무조건하게)

```html
<input type="text" minlength="4" maxlength="8" required placeholder="입력" />
```

- Input 태그의 속성을 사용하기위해서는 form 태그와 결합하여 사용

```html
<form>
  <label for="name"
    >Enter your name: <input type="text" name="name" id="name" required />
  </label>
</form>
```

## [참고링크](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Input)

## label 태그

- Input 태그와 연결이 가능

```html
<label for="username">Click me</label> <input type="text" id="username" />
```

> label의 for에는 input의 아이디 값 설정

- label태그는 input 태그와 중첩해서 사용가능

```html
<label
  >Do you like peas?
  <input type="checkbox" name="peas" />
</label>
```

## [참조링크](https://developer.mozilla.org/ko/docs/Web/HTML/Element/label)

# form 태그 상세

> name 속성을 input 내에 사용할시 url 형태로 서버에 요청을 할수있음 (서버에 데이터로 요청할수있음 )

```html
<form action="/hello">
  <!-- name 속성사용시 submit 을 할때  /hello/username="text내부의값" 형태로 서버에 요청할수있음  -->
  <input name="username" type="text" />
  <button>제출</button>
</form>
```
