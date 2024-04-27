<script setup>
  const props = defineProps(["cadastraTarefa", "tarefaTemp", "trocarFiltro", "editaTarefaTemp"]);
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
      <div class="row">
        <div class="col">
          <input :value="props.tarefaTemp" @change="props.editaTarefaTemp"
              required type="text" placeholder="Digite aqui a descrição da tarefa" class="form-control mb-4 p-2">
        </div>
        <div class="col-md-2">
          <button class="btn p-2" type="submit">Cadastrar</button>
        </div>
        <div class="col-md-2">
          <select @change="props.trocarFiltro" class="form-control p-2 text-center select">
            <option class="todas" value="todas">Todas</option>
            <option class="pendentes" value="pendentes">Pendentes</option>
            <option class="finalizadas" value="finalizadas">Finalizadas</option>
          </select>
        </div>
      </div>
    </form>
</template>

<style scoped>
  .btn {
    color: #fff;
    background-color: #155956;
    cursor: pointer;
  }

  .btn:hover {
    background-color: #1f827d;
    color: #fff;
  }

  .row .col input {
    outline-color: #155956 !important;
  }

  .select {
    cursor: pointer;
    background-color: rgba(21,89,86, 0.2);
    transition: all ease-in-out .2s;
  }

  .select:hover {
    background-color: rgba(0, 0, 0, 0.1);
    transition: all ease-in-out .2s;
  }

  @media screen and (max-width: 767px) {
    .btn {
      width: 100%;
      margin-bottom: 20px;
    }
  }
</style>