<script setup>
  const props = defineProps(["cadastraTarefa", "tarefaTemp", "trocarFiltro", "editaTarefaTemp"]);
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
      <div class="row">
        <div class="col">
          <input :value="props.tarefaTemp" @change="props.editaTarefaTemp"
              required type="text" placeholder="Digite aqui a descrição da tarefa" class="form-control mb-4">
        </div>
        <div class="col-md-2">
          <button class="btn btn-primary" type="submit">Cadastrar tarefa</button>
        </div>
        <div class="col-md-2">
          <select @change="props.trocarFiltro" class="form-control">
            <option class="todas" value="todas">Todas</option>
            <option class="pendentes" value="pendentes">Pendentes</option>
            <option class="finalizadas" value="finalizadas">Finalizadas</option>
          </select>
        </div>
      </div>
    </form>
</template>