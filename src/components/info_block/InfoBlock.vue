<template>
    <div :class="['block-container', imgLeft ? '' : 'row-reverse',hasGutter ? 'hasGutter' : '']">
        <div class="text-block">
            <h3 class="block_title">{{ title }}</h3>
            <slot></slot>
        </div>
        <img class="block_img" :src="imgUrl" alt="img">
    </div>
</template>
  
<script setup lang="ts">


interface BlockProps {
    title: string;
    imgUrl: string;
    imgLeft?: boolean;
    hasGutter?: boolean;
}
const props = defineProps<BlockProps>();
</script>
  
<style scoped>
.block-container {
    display: flex;
    align-items: start;
    justify-content: space-between;
    flex-direction: row-reverse;
    gap: 30px;
    padding: 0 165px;

    &.hasGutter{
        margin-bottom:78px;
    }

    &.row-reverse {
        flex-direction: row;
    }

    &>.block_img {
        flex: 0 0 455px;
        height: 455px;
        border-radius: 10px;

        @media only screen and (max-width: 1284px) {
            & {
                flex: 0 0 345px;
                height: 345px;
            }
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
        }


    }

}

:deep >span {
    color: #2B2B2B;
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 30px;
    letter-spacing: 0.089px;
}
</style>
