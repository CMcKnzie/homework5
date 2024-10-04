<script setup>

import { ref } from 'vue'

const pages = ref(10)
const activePage = ref(5)

const prev = () => {
    if (activePage.value > 1) {
        activePage.value--
        console.log(activePage.value)
    }
}

const next = () => {
    if (activePage.value < pages.value) {
        activePage.value++
        console.log(activePage.value)
    }
}


</script>

<template>
    <div>
        <button @click="prev" :disabled="activePage === 1">PREV</button>

        <button v-for="page in pages" :key="page" class="">{{ page }}</button>

        <button @click ="next" :disable="activePage ===pages" >NEXT</button>
    </div>
</template>