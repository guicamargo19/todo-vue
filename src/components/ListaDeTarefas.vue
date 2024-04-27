<script setup>
  const props = defineProps(["tarefas"]);
</script>

<template>
    <ul class="list-group mt-4">
      <li class="list-group-item mb-1" v-for="tarefa in props.tarefas">
        <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
        <label :class="{ done: tarefa.finalizada }" class="ms-3 item" :for="tarefa.titulo">
          {{ tarefa.titulo }}
        </label>
      </li>
    </ul>
</template>

<style scoped>
  .done {
    text-decoration: line-through;
    color: darkgrey;
  }

  .list-group-item {
    border-radius: 4px;
  }

  .item {
    cursor: pointer;
  }
</style>