<template>
    <div :class="['block-container', imgLeft ? '' : 'row-reverse', hasGutter ? 'hasGutter' : '']">
        <div class="text-block">
            <h3 class="block_title">{{ title }}</h3>
            <slot></slot>
        </div>
        <img class="block_img" :src="imgUrl" alt="img">
    </div>
</template>
  
<script  lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props: {
        title: {
            type: String,
            required: true
        },
        imgUrl: {
            type: String,
            required: true
        },
        imgLeft: {
            type: Boolean,
            required: false
        },
        hasGutter: {
            type: Boolean,
            required: false
        }
    },

});
</script>
  
<style scoped>
.block-container {
    display: flex;
    align-items: start;
    justify-content: space-between;
    flex-direction: row-reverse;
    gap: 30px;
    padding: 0 165px;

    @media only screen and (max-width: 1028px) and (min-width:1025px) {
        flex-direction: column-reverse;
        padding: 0 30px;
    }

    @media only screen and (max-width: 1024px) {
        flex-direction: column-reverse !important;
        padding: 0 15px;
    }

    &.hasGutter {
        margin-bottom: 78px;
    }

    &.row-reverse {
        flex-direction: row;
    }

    &>.block_img {
        flex: 0 0 455px;
        height: 455px;
        border-radius: 10px;
        width: 100%;

        @media only screen and (max-width: 784px) {

            flex: 1;

        }

        @media only screen and (max-width: 1284px) and (min-width: 785px) {

            flex: 0 0 345px;
            height: 345px;

        }

    }

    &>.text-block {
        display: flex;
        flex-direction: column;
        flex: 1;

        &>.block_title {
            color: #2B2B2B;
            font-size: 36px;
            font-style: normal;
            font-weight: 400;
            line-height: normal;
            letter-spacing: 0.16px;
            margin-top: 0;
            margin-bottom: 30px;

            @media only screen and (max-width: 1024px) {
                text-align: center;
            }
        }


    }

}

:deep>span {
    color: #2B2B2B;
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 30px;
    letter-spacing: 0.089px;
}
</style>
