<script setup>
    const props = defineProps(['tarefasPendentes']);
</script>

<template>
    <header class="p-1 mb-4 mt-4 bg-dark color rounded-3 d-flex justify-content-between align-items-center">
        <h1 class="title">To Do List</h1>
        <p class="tasks">Você possui {{ props.tarefasPendentes }} tarefas pendentes</p>
    </header>
</template>

<style scoped>
  .color {
    color: darkgrey;
  }

  .title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 120px !important;
    margin: 0;
    padding-top: 10px;
    padding-left: 30px;
  }

  .tasks {
    padding-top: 110px;
    padding-right: 20px;
    margin: 0;
  }

  @media screen and (min-width: 768px) and (max-width: 1023px) {
    .title {
      font-size: 90px !important;
    }

    .tasks {
      padding-top: 50px;
      padding-right: 20px;
      margin: 0;
    }
  }

  @media screen and (max-width: 767px) {
    .title {
      font-size: 50px !important;
      padding-left: 10px;
    }

    .tasks {
      padding-top: 26px;
      padding-right: 5px;
      font-size: 10px;
      margin: 0;
    }
  }
</style>