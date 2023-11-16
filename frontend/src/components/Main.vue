<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">
import axios from 'axios';
import { onMounted, ref } from 'vue';

interface Chave {
    nome: string;
    situacao: string;
    status: boolean
}

const listKey = ref<Chave[]>([])
const key = ref('')

const fetchData = async () => {
    try {
        const response = await axios.get('http://localhost:3000/chave')
        listKey.value = response.data as Chave[]
    } catch (error) {
        console.error("Erro na requisição à API: ", error)
    }
}

onMounted(() => {
    fetchData()
})
</script>

<template>
    <main>
        <select v-model="key" id="selectKey">
            <option value="" disabled selected hidden>Selecione uma chave</option>
            <option v-for="chave in listKey" :value="chave">{{ chave.nome }}</option>
        </select>
    </main>
</template>

<style scoped>
main {
    display: flex;
    padding: 4rem;
    align-items: center;
    justify-content: space-around;
}

select {
    cursor: pointer;
    appearance: none;
    padding: 1rem 4rem;
    border-radius: 2rem;
    text-align: center;
    font-size: 18px;
    background-color: #50BF84;
}
</style>