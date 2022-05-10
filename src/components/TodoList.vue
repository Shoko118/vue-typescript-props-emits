<script setup lang="ts">
import type { Todos } from "../Interface/interface";

interface Props {
  todos: Todos[];
}

const props = defineProps<Props>();
</script>

<template>
  <div>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <div>{{ todo.name }}</div>
      </li>
    </ul>
  </div>
</template>
