<template>
  <div>
    <h1> My Task Manager</h1>
    <TaskForm @add-task="addTask" />
    <TaskItem
      v-for="task in taskList"
      :key="task.index"
      :task="task"
      @toggle-completed="toggleTaskComplete"/>
  </div>
</template>

<script setup>
import { reactive} from 'vue';
import TaskForm from './TaskForm.vue';
import TaskItem from './TaskItem.vue';

const taskList = reactive([]);

const addTask = (task) => {
  // const index = this.taskList.length + 1;
  taskList.push({
    task,
    isCompleted: null
  });
};
const toggleTaskComplete = (task) => {
  taskList[task].isCompleted = !taskList[task].isCompleted;
}
</script>

<style>

</style>
