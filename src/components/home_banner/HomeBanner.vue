<script setup lang="ts">

</script>
<template>
    <img class="img_landing" src="/home-baner.png" alt="home-landing">
</template>

<style scoped>
.img_landing {
    width: 100%;
    min-height: 200px;
    object-fit: cover;
    animation: fadeIn 0.7s ease-out;
}

@keyframes fadeIn {
    0% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}
</style>
