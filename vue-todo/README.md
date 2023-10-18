# vue-todo

## 구현할 기능
- 할 일 조회
- 할 일 추가
- 할 일 삭제
- 할 일 수정

## 할 일 추가
- data를 `App.vue`에서 정의 한 후 `TodoInput.vue`로 전달 (props)
- `TodoInput.vue`에서 props type 등 정의
- `TodoInput.vue`에서 입력 행위가 발생하면 `$emit(input)`에 의해 `App.vue`로 이벤트 전파 
- `App.vue`에서는 `@input`으로 이벤트 수신
- 추가 버튼을 누르면 `$emit("add")`에 의해 `App.vue`로 이벤트 전파
- `App.vue`에서는 `@add`으로 이벤트 수신
- `App.vue`에서 data를 `localStorage`에 저장하고 data 초기화
