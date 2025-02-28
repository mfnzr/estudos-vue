<script setup lang="ts">
import Cronometro from './Cronometro.vue';

</script>

<template>
    <div class="box has=text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                {{ tarefa.descricao }}
            </div>
            <div class="column">
                <CronometroComponent :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>

    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import CronometroComponent from './Cronometro.vue';
import iTarefa from './interfaces/iTarefa';

export default defineComponent({
    name: 'TarefaComponent',
    components: {
        CronometroComponent
    },
    props: {
        tarefa: {
            type: Object as PropType<iTarefa>,
            required: true
        }
    }
})
</script>