<script setup>
defineProps({
    title: String
})
const emits = defineEmits(["btnClick"])
</script>

<template>
    <!-- <button @click="emits('btnClick')" class="my-button">{{title}}</button> -->
    <button class="my-button"><slot>

    </slot></button>
</template>

<style scoped>
.my-button {
    /* background-color: lightblue; */
    background: linear-gradient(0.25turn, purple, lightblue);
    border-color: black;
    margin: 20px;
}
</style>
