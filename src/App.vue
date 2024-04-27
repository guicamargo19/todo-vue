<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Formulario from './components/Formulario.vue';
  import ListaDeTarefas from './components/ListaDeTarefas.vue';
  import Footer from './components/Footer.vue';

  const estado = reactive({
    filtro: "todas",
    tarefaTemp: '',
    tarefas: [
      {
        titulo: 'Integrar API Django com Python no projeto ReactJS com TypeScript',
        finalizada: false,
      },
      {
        titulo: 'Utilizar GitHub Actions para CI/CD',
        finalizada: true,
      },
      {
        titulo: 'Fazer deploys dos projetos na Google Cloud Platform',
        finalizada: false,
      },
    ]
  })

  const getTarefasPendentes = () => {
    return estado.tarefas.filter(tarefa => !tarefa.finalizada);
  }

  const getTarefasFinalizadas = () => {
    return estado.tarefas.filter(tarefa => tarefa.finalizada);
  }

  const getTarefasFiltradas = () => {
    const { filtro } = estado;

    switch(filtro) {
      case 'pendentes':
        return getTarefasPendentes();
      case 'finalizadas':
        return getTarefasFinalizadas();
      default:
        return estado.tarefas;
    }
  }

  const cadastraTarefa = () => {
    const novaTarefa = {
      titulo: estado.tarefaTemp,
      finalizada: false,
    }
    estado.tarefas.push(novaTarefa);
    estado.tarefaTemp = '';
  }
</script>

<template>
  <div class="container">
    <Cabecalho :tarefas-pendentes="getTarefasPendentes().length" />
    <Formulario :trocar-filtro="evento => estado.filtro = evento.target.value" :tarefa-temp="estado.tarefaTemp" :edita-tarefa-temp="evento => estado.tarefaTemp = evento.target.value" :cadastra-tarefa="cadastraTarefa"/>
    <ListaDeTarefas :tarefas="getTarefasFiltradas()"/>
    <Footer></Footer>
  </div>
</template>