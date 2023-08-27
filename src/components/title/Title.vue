<template>
    <h1 :class="titleClasses">{{ title, isMain }}</h1>
</template>
  
<script  lang="ts">
import { computed, defineComponent } from 'vue';



export default defineComponent({
    props: {
        title: {
            type: String,
            required: true
        },
        isMain: {
            type: Boolean,
            required: false
        }
    },
    setup(props) {
        const titleClasses = computed(() => ({
            'section-title': true,
            'main-title': props.isMain
        }));

        return {
            titleClasses
        };
    }

});
</script>
  
<style scoped>
.section-title {
    margin-top: 74px;
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
  