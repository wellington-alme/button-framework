<template>
  <ul>
    <TaskItem 
      v-for="(tarefa, index) in tarefas" 
      :key="index" 
      :tarefa="tarefa" 
      @remover="$emit('remover', index)" 
    />
  </ul>
</template>

<script setup>
import TaskItem from 'todo-vue/src/components/TaskItem.vue'
defineProps(['tarefas'])
</script>
