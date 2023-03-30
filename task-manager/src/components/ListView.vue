<template>
  <div>
    <div class="box">
      <h1> My Task Manager</h1>
      <TaskForm @add-task="addTask" />
      <TaskItem
      v-for="task in taskList"
      :key="task.index"
      :task="task"
      @toggle-completed="toggleTaskComplete(task)"/>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue';
import TaskForm from './TaskForm.vue';
import TaskItem from './TaskItem.vue';

const taskList = reactive([]);

const addTask = (task) => {
  taskList.push({
    task,
    isCompleted: false,
    index: 0,
  });
};
const toggleTaskComplete = (task) => {
  task.isCompleted = !task.isCompleted;
}
</script>

<style>
.box {
  width: 20%;
  margin: auto;
  align-items: center;
  padding: 3%;
  background-color: #f1f1f1;
  box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1),
    0 8px 10px -6px rgb(0 0 0 / 0.1);
}
</style>
