<script setup>
import MyButton from "./components/MyButton.vue";
import Count from "./components/Count.vue";

function onButtonClick(message){
  alert (message);
}
</script>

<template>
  <!-- <MyButton class="my-button-red" :title="'Bouton 1'" @btnClick="onButtonClick('Bouton 1')"></MyButton>
  <MyButton :title="'Chill Kévin'" @btnClick="onButtonClick('Faut sleep la nuit')"></MyButton>
  <MyButton :title="'Ca groove ?'" @btnClick="onButtonClick('Yknow man')"></MyButton> -->
  <Count></Count>
</template>

<style scoped>
.my-button-red{
  background: red;
}
</style>
