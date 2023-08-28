<template>
    <div class="grid-container">
        <div class="card" v-for="(item, index) in images" :key="index">

            <img loading="lazy" class="item" :src="item.imgUrl" />
        </div>
    </div>
</template>
    
<script lang="ts">
import { defineComponent, PropType } from 'vue';


interface Item {
    imgUrl?: string;
}



export default defineComponent({
    props: {
        images: {
            type: Array as PropType<Item[]>,
            required: true
        }
    },

});
</script>
  


<style>
.grid-container {
    padding-top: calc(107px + 74px);
    padding-bottom: 100px;
    display: flex;
    --gap: 30px;
    --itemByScreen: 4;
    gap: var(--gap);
    margin: 0 auto;
    overflow: hidden;
    flex-wrap: wrap;
    justify-items: flex-start;

    @media only screen and (max-width: 1024px) {
        --gap: 10px;
        --itemByScreen: 2;
    }

    @media only screen and (max-width: 1280px) and (min-width: 1025px) {
        --gap: 20px;
        --itemByScreen: 3;
    }


    &>.card {
        width: calc((1 / var(--itemByScreen) * 100%) - var(--gap));
        padding-left: var(--gap);

        &>.item {

            width: 100%;
        }
    }


}
</style>

  