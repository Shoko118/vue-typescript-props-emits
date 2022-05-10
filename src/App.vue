<script setup lang="ts">
import TodoList from "./components/TodoList.vue";
import TodoButton from "./components/TodoButton.vue";
import { Todos } from "./Interface/interface";
import { ref } from "vue";

const inputText = ref("");
const id = ref(0);
const todos = ref<Todos[]>([
  { id: 1, name: "HTML", completed: false },
  { id: 2, name: "CSS", completed: false },
]);

function addButton() {
  if (inputText.value === "") return;

  const newTodos = {
    id: id.value++,
    name: inputText.value,
    completed: false,
  };

  todos.value.push(newTodos);
  inputText.value = "";
}
</script>

<template>
  <h1>Todo App with Typescript</h1>

  <input type="text" placeholder="enter a todo" v-model="inputText" />
  <TodoButton @add-button="addButton" v-model="inputText" />
  <TodoList :todos="todos" />
</template>
