<script setup>
import { ref } from 'vue';
import MyButton from "./components/MyButton.vue";
import Count from "./components/Count.vue";
import Moto from './components/Moto.vue';

function onButtonClick(message){
  alert (message);
}

// function onCountUpdate(valeur){
//   console.log("Valeur : ", valeur)
// }

const valeur = ref(0)

const data = ref([
  {
    marque: "bmw",
    couleur: "blanche",
    cssColor: "lightgray"
  },
  {
    marque: "flippingDaBurgir",
    couleur: "violet FLUO",
    cssColor: "purple"
  }
])

const formData = ref({
  marque:"",
  couleur:"",
  cssColor:""
})

function onSubmit(){
  data.value.push(formData.value);
  formData.value = ref({
  marque:"",
  couleur:"",
  cssColor:""
})
}
</script>

<template>
  {{ valeur }}
  <!-- <MyButton :title="'Reset'" @click = "valeur = 0"></MyButton> -->
  <MyButton @click = "valeur = 0">
    <template #icon>
      +
    </template>
    Reset
  </MyButton>

  <!-- <MyButton class="my-button-red" :title="'Bouton 1'" @btnClick="onButtonClick('Bouton 1')"></MyButton>
  <MyButton :title="'Chill Kévin'" @btnClick="onButtonClick('Faut sleep la nuit')"></MyButton>
  <MyButton :title="'Ca groove ?'" @btnClick="onButtonClick('Yknow man')"></MyButton> -->

  <!-- <Count @countUpdate="onCountUpdate"></Count> -->

  <Count v-model="valeur"></Count>

  <form @submit.prevent = "onSubmit">
    <label for="marque">Marque : </label>
    <input type="text" id="marque" v-model="formData.marque">
    <br>
    <label for="couleur">Couleur : </label>
    <input type="text" id="couleur" v-model="formData.couleur">
    <br>
    <label for="cssColor">Couleur CSS : </label>
    <input type="color" id="cssColor" v-model="formData.cssColor">
    <br>
    <MyButton>Ajouter</MyButton>
  </form>


  <Moto v-for="moto of data" :marque="moto.marque" :couleur="moto.couleur" :cssColor="moto.cssColor">
  </Moto>
</template>

<style scoped>
.my-button-red{
  background: red;
}
</style>
