<template>
  <div>
    <h1>Lista de Tarefas</h1>
    <input v-model="novaTarefa" placeholder="Digite uma tarefa" />
    <button @click="adicionarTarefa">Adicionar</button>
    <TaskList :tarefas="tarefas" @remover="removerTarefa" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import TaskList from 'todo-vue/src/components/TaskList.vue'

const novaTarefa = ref('')
const tarefas = ref([])

function adicionarTarefa() {
  if (novaTarefa.value.trim() !== '') {
    tarefas.value.push(novaTarefa.value)
    novaTarefa.value = ''
  }
}

function removerTarefa(index) {
  tarefas.value.splice(index, 1)
}
</script>
<style scoped>
li {
  list-style: none;
  padding: 8px;
  margin-bottom: 5px;
  background-color: #f3f3f3;
  border-radius: 5px;
}
button {
  margin-left: 10px;
  background: #ff4d4d;
  border: none;
  color: white;
  cursor: pointer;
}
</style>
