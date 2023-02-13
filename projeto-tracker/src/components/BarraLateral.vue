<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="logo teste do tracker" width="140">
        </h1>
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
        background: #1c9c7ce3;
        width: 100%;
        height: 100vh;
        padding: 20px;
    }

    @media only screen and (max-width: 768px) {
        header {
            padding: 2.5em;
            height: auto;
        }
    }
</style>