<script setup lang="ts">
function getAddButton() {
  emit("addButton");
}

const emit = defineEmits<{
  (emit: "addButton"): void;
}>();
</script>

<template>
  <div>
    <button @click="getAddButton">Add</button>
  </div>
</template>
