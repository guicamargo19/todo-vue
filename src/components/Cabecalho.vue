<script setup>
    const props = defineProps(['tarefasPendentes']);
</script>

<template>
    <header class="p-5 mb-4 mt-4 bg-dark color rounded-3">
        <h1>To do List</h1>
        <p>Você possui {{ props.tarefasPendentes }} tarefas pendentes</p>
    </header>
</template>

<style scoped>
  .color {
    color: darkgrey;
  }
</style>