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
    padding-top: 74px;
    padding-bottom: 74px;
    margin: 0;
    color: #2B2B2B;
    font-size: 58px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.258px;
    text-align: center;

    @media screen and (max-width:1024px) {
        font-size: 46px;
        font-style: normal;
        font-weight: 400;
        line-height: 53px;
        /* 115.217% */
        letter-spacing: 0.204px;
    }

    &.main-title {
        padding-top: 112px;
        padding-bottom: 103px;
    }

}
</style>
  