<template>
    <h1 :class="titleClasses">{{ title, isMain }}</h1>
</template>
  
<script setup lang="ts">
import { computed } from 'vue';

interface TitleProps {
    isMain?: boolean;
    title: string;
}

const props = defineProps<TitleProps>();

const titleClasses = computed(() => {
    return {
        'section-title':true,
        'main-title': props.isMain,
    };
});
</script>
  
<style scoped>
.section-title {
    margin-top:74px;
    margin-bottom: 74px;
    color: #2B2B2B;
    font-size: 58px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.258px;
    text-align: center;
    &.main-title {
        margin-top: 112px;
        margin-bottom: 103px;
    }
}
</style>
  