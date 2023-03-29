<template>
 <li>
  <input type="checkbox"
  :checked="task.IsCompleted"
  @input="$emit('toggleCompleted', index)"
  />
  <div class="todo">
    <span :class="{'completed-task': task.isCompleted}">
    {{ task.task }}
    </span>
  </div>
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
    }
});

</script>

<style>

</style>
