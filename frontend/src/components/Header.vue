<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">
import { ref } from 'vue';

const title = ref('Where\'s the key?')
</script>

<template>
    <header>
        <img class="logo" src="../assets/logo.png" alt="Key logo" width="150" height="150" />

        <div class="title">
            <h1>{{ title }}</h1>
        </div>
    </header>
</template>

<style scoped>
header {
    display: flex;
    padding: 0.5rem 3rem 0.5rem 3em;
    align-items: center;
    background-color: #50BF84;
}

.title {
    font-size: 1.5rem;
    width: 80%;
}

h1 {
    padding-top: 1em;
}
</style>
