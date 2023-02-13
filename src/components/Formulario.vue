<template>
    <div class="box">
        <div class="columns">
            <div class="column id-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa deseja iniciar?">
            </div>
            <div class="column">
                <Temporizador />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import Temporizador from "./Temporizador.vue";

    export default defineComponent ({
        name: 'Formulario',
        components: {
            Temporizador
        },
        
    })
</script>

<style>
    .box {
        box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.377);
    }
</style>
