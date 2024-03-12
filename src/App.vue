<script setup>
import { ref } from 'vue';
import MyButton from "./components/MyButton.vue";
import Count from "./components/Count.vue";

function onButtonClick(message){
  alert (message);
}

// function onCountUpdate(valeur){
//   console.log("Valeur : ", valeur)
// }

const valeur = ref(0)
</script>

<template>
  {{ valeur }}
  <!-- <MyButton :title="'Reset'" @click = "valeur = 0"></MyButton> -->
  <MyButton @click = "valeur = 0">Reset</MyButton>

  <!-- <MyButton class="my-button-red" :title="'Bouton 1'" @btnClick="onButtonClick('Bouton 1')"></MyButton>
  <MyButton :title="'Chill Kévin'" @btnClick="onButtonClick('Faut sleep la nuit')"></MyButton>
  <MyButton :title="'Ca groove ?'" @btnClick="onButtonClick('Yknow man')"></MyButton> -->

  <!-- <Count @countUpdate="onCountUpdate"></Count> -->

  <Count v-model="valeur"></Count>
</template>

<style scoped>
.my-button-red{
  background: red;
}
</style>
