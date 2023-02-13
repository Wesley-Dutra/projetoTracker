<template>
    <div class="box">
        <div class="columns">
            <div class="column id-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa deseja iniciar?">
            </div>
            <div class="column">
                <section class="is-flex is-align-items-center is-justify-content-space-between">
                    <section>
                        <strong>
                            {{ tempoDecorrido }}
                        </strong>
                    </section>
                    <button class="button" @click="iniciar">
                        <span class="icon">
                            <i class="fas fa-play"></i>
                        </span>
                        <span>Iniciar</span>
                    </button>
                    <button class="button" @click="finalizar">
                        <span class="icon">
                            <i class="fas fa-stop"></i>
                        </span>
                        <span>Parar</span>
                    </button>
                </section>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent ({
        name: 'FormularioTempo',
        data() {
            return {
                tempoEmSegundos: 0,
                cronometro: 0
            }
        },
        computed: {
            tempoDecorrido () : string {
                return new Date(this.tempoEmSegundos*1000).toISOString().substr(11, 8)
            }
        },
        methods: {
            iniciar () {
                //começar a contagem
                this.cronometro = setInterval(()=>{
                    this.tempoEmSegundos += 1;
                }, 1000)
            },
            finalizar () {
               //finalizar a contagem 
               clearInterval(this.cronometro)
            }
        },
    })
</script>

<style>
    .box {
        box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.377);
    }
</style>
