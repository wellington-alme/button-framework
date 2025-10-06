<template>
  <li>
    {{ tarefa }}
    <button @click="$emit('remover')">Remover</button>
  </li>
</template>

<script setup>
defineProps(['tarefa'])
</script>
