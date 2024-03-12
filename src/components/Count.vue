<script setup>
import { ref, watch } from 'vue';
import MyButton from './MyButton.vue';

//const valeur = ref(0)
const valeur = defineModel()
const emits = defineEmits(["countUpdate"])

watch(valeur,function(newValeur){
    emits("countUpdate", newValeur)
})
// function increment(){
//     valeur.value ++;
// }
// function decrement(){
//     valeur.value --;
// }
</script>

<template>
    <div class="count">
        <!-- <MyButton :title="'+'" @click ="valeur++"/> -->
        <MyButton @click ="valeur++">+</MyButton>
        {{ valeur }}
        <!-- <MyButton :title="'-'" @click ="valeur--"/> -->
        <MyButton @click ="valeur--">-</MyButton>
    </div>
</template>

<style scoped>
.count{
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>