<template>
  <div>
    <h1> My Task Mangager</h1>
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
  const index = this.taskList.length + 1;
  taskList.push({
    index,
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
