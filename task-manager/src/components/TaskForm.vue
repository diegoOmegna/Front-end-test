<template>
  <div class="task-input">
    <input
    v-model="newTask.task"
    @keyup.enter="addTask"
    type="text"
    placeholder="Add a new task"
    />
  </div>
</template>

<script setup>

import { defineEmits, reactive } from "vue";


const emit = defineEmits(["add-task"])

const newTask = reactive({
  task: ""
});
const addTask = () => {
  if (newTask !== null) {
    emit("add-task", newTask.task);
    addTask.task = "";
    return;
  }
};
</script>

<style>

</style>
