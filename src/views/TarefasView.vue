<template>
  <h1>Minhas tarefas</h1>

  <div class="form">
    <input
      v-model.trim="novaTarefa"
      @keyup.enter="adicionar"
      placeholder="Digite uma tarefa"
    />
    <button @click="adicionar">Adicionar</button>
  </div>

  <p v-if="tarefas.length === 0">Nenhuma tarefa cadastrada.</p>

  <ul>
    <li v-for="tarefa in tarefas" :key="tarefa.id">
      {{ tarefa.titulo }}
    </li>
  </ul>
</template>

<script setup>
import { ref } from 'vue'

const novaTarefa = ref('')
const tarefas = ref([])

function adicionar() {
  if (novaTarefa.value === '') return   

  tarefas.value.push({
    id: Date.now(),
    titulo: novaTarefa.value
  })

  novaTarefa.value = ''                 
}
</script>

<style scoped>
.form {
  display: flex;
  gap: 8px;
  justify-content: center;
  margin-bottom: 16px;
}
input {
  padding: 8px;
  width: 60%;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  padding: 8px;
  border-bottom: 1px solid #eee;
}
</style>
