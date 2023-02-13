<template>
    <header>
        <div class="text-center">
            <img src="../assets/logo.png" alt="logo teste do tracker" id="logo">
        </div>
    </header>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent ({
        name: 'BarraLateral'
    })
</script>

<style scoped>
    header {
        background: #019367e3;
        width: 100%;
        height: 100vh;
        padding: 10px;
    }

    #logo {
        width: 150px;
    }

    @media only screen and (max-width: 768px) {
        header {
            padding: 15px;
            height: auto;
        }

        .text-center {
            text-align: center;
        }

        #logo {
            width: 150px;
            margin: auto;
        }
    }
</style>