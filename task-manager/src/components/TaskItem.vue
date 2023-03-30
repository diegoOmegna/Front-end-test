<template>
 <li :class="{'completed-task': task.isCompleted}">
  <input type="checkbox"
  :checked="task.IsCompleted"
  @input="$emit('toggleCompleted', index)"
  />
    <span >
    {{ task.task }}
    </span>
 </li>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';
defineEmits(["toggle-completed"])
defineProps({
  task: {
    type: Object,
    required: true
    },
  index: {
    type: Number,
    required: true
  },
  isCompleted: {
    type: Boolean,
    required: true
  }

});

</script>
<style>
li {
  margin-top: 5%;
  display: flex;
  flex:none;
  align-items: center;
  gap: 10px;
  padding: 16px 10px;
  background-color: white;
  box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1),
    0 8px 10px -6px rgb(0 0 0 / 0.1);
}
.completed-task {
  opacity: 0.3;
}
input[type=checkbox] {
width: auto;
}

</style>
