<template>
    <div class="column">
        <section class="is-flex is-align-items-center is-justify-content-space-between">
            <Cronometro :tempoEmSegundos="tempoEmSegundos"/>
            <button class="button" @click="iniciar" :disabled="cronometroRodando">
                <span class="icon">
                    <i class="fas fa-play"></i>
                </span>
                <span>Iniciar</span>
            </button>
            <button class="button" @click="finalizar" :disabled="!cronometroRodando">
                <span class="icon">
                    <i class="fas fa-stop"></i>
                </span>
                <span>Parar</span>
            </button>
        </section>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import Cronometro from "./Cronometro.vue";

    export default defineComponent ({
        name: 'Temporizador',
        components: {
            Cronometro
        },
        data() {
            return {
                tempoEmSegundos: 0,
                cronometro: 0,
                cronometroRodando: false
            }
        },

        methods: {
            iniciar () {
                //começar a contagem
                this.cronometro = setInterval(()=>{
                    this.tempoEmSegundos += 1;
                }, 1000)
                this.cronometroRodando = true
            },
            finalizar () {
               //finalizar a contagem 
               clearInterval(this.cronometro)
               this.cronometroRodando = false
            }
        },
    })
</script>