<script setup>
defineProps({
    title: String
})
const emits = defineEmits(["btnClick"])
</script>

<template>
    <button @click="emits('btnClick')" class="my-button">{{title}}</button>
</template>

<style scoped>
.my-button {
    background-color: lightblue;
    margin: 20px;
}
</style>
