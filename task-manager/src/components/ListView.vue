<template>
  <div>
    <h1> My Task Mangager</h1>
    <TaskForm @add-task="addTask" />
    <TaskItem
      v-for="task in taskList"
      :key="task.id"
      :task="task"
      @toggle-complete="toggleTaskComplete"/>
  </div>
</template>

<script setup>
import { reactive} from 'vue';
import TaskForm from './TaskForm.vue';
import TaskItem from './TaskItem.vue';

const taskList = reactive([]);

const addTask = (task) => {
  const id = `${Date.now()}-${Math.floor(Math.random() * 1000000)}`;
  taskList.push({
    id,
    task,
    isCompleted: null
  });
};
const toggleTaskComplete = (task) => {
  taskList[task.id].isCompleted = !taskList[task.id].isCompleted;
}
</script>

<style>

</style>
