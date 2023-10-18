<template>
  <div>
    <label for="todo-input">오늘 할 일 : </label>
    <input id="todo-input" type="text" :value="item" @input="handleInput" />
    <button @click="addTodo" type="button">추가</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  // props: ["item"],
  // props에 대한 validation
  props: {
    item: {
      type: String,
      required: true,
    },
  },
  methods: {
    handleInput(event: InputEvent) {
      //input event가 일어날 때 데이터 갱신
      //event target이 html input element라고 알려줌
      const eventTarget = event.target as HTMLInputElement;
      this.$emit("input", eventTarget.value);
    },
    addTodo() {
      //add라는 이벤트 발생 -> app.vue로 전파
      this.$emit("add");
    },
  },
});
</script>

<style scoped></style>
