<script setup>
defineProps({
    marque: String,
    couleur: String,
    cssColor: String
})
</script>

<template>
    <div>
        <ul>
            <li>
                Marque : {{ marque }}
            </li>
            <li>
                Couleur : {{ couleur }}
                <span 
                    class="color-span" :style="{
                        backgroundColor : cssColor
                    }">
                </span>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.color-span{
    display: inline-block;
    width: 2rem;
    height: 1rem;
    border: 1px black solid;
    border-radius: 0.5rem;
}
</style>