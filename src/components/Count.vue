<script setup>
import { ref } from 'vue';
import MyButton from './MyButton.vue';

const valeur = ref(0)

// function increment(){
//     valeur.value ++;
// }
// function decrement(){
//     valeur.value --;
// }
</script>

<template>
    <div class="count">
        <MyButton :title="'+'" @click ="valeur++"/>
        {{ valeur }}
        <MyButton :title="'-'" @click ="valeur--"/>
    </div>
</template>

<style scoped>
.count{
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>