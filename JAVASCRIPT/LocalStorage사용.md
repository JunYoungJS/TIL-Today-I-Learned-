# LocalStorage 사용

- SessionStorage 와다르게 데이터가 만료되지 않음
- 페이지를 새로고침했을떄 웹 페이지 내의 입력한 데이터가 사라지지 않도록 할수있게함
- localstorage.setItem('key값','value'값)

  > 로컬스토리지 내에 key value형태로 저장

- localstorage.getItem('key값')

  > key값을 기반으로 저장된 value값을 가져올수있음

- localstorage.removeItem('key값')

  > 해당 key값의 value를 제거할수있음

- localstorage.clear()

  > 해당 로컬저장소의 모든 키 벨류값을 제거 함

- 데이터베이스 대용으로 사용 (중요하지 않은 데이터 저장 )
- 문자형 데이터 타입만을 지원
