<script setup lang="ts">

defineProps<{ title?: string }>()
</script>

<template>
    <img class="img_landing" src="/home-baner.png" alt="home-landing">
</template>

<style scoped>
.img_landing{
    width:100%;
    min-height:200px;
    object-fit:cover;
}
</style>
