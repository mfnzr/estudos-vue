<template>
  <main class="columns is-gapless is-multiline">
    <div class="colum is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <FormularioTarefa @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <TarefaComponent v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>

      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import FormularioTarefa from './components/FormularioTarefa.vue';
import TarefaComponent from './components/TarefaComponent.vue';
import iTarefa from './components/interfaces/iTarefa';

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioTarefa,
    TarefaComponent
  },
  data() {
    return {
      tarefas: [] as iTarefa[]
    }
  },
  methods: {
    salvarTarefa(tarefa: iTarefa) {
      this.tarefas.push(tarefa);
    }
  }

});
</script>

<style></style>
