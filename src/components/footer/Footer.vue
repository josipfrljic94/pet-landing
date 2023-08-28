<template>
    <section class="footer">
        <div class="footer-container">
            <div class="card" v-for="(footerCategory, index) in footerCategories" :key="index">
                <FooterCategory :footerCategory="footerCategory" />
            </div>
        </div>
        <span class="footer-policy">
            Copyright is a legal right, existing in many countries, that grants the creator of an original work exclusive
            rights to determine whether, and under what conditions, this original work may be used by others.
        </span>
    </section>
</template>
    
<script lang="ts">
import { defineComponent, PropType } from 'vue';
import FooterCategory from './FooterCategory.vue';


interface FooterCategory {
    title: string;
    footerItems: string[];
}



export default defineComponent({
    components: {
        FooterCategory
    },
    props: {
        footerCategories: {
            type: Array as PropType<FooterCategory[]>,
            required: true
        }
    },

});
</script>
  


<style>
.footer {
    background-color: #1D1D1D;
    box-shadow: 0 0 0 100vmax #1D1D1D;
    clip-path: inset(0 -100vmax);
    max-width: 920px;
    margin: 0 auto;
    padding: 74px 0;

    &>.footer-container {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        gap: 30px;
        padding-bottom: 50px;
        flex-wrap: wrap;
    }

    &>.footer-policy {
        width: 100%;
        display: inline-block;
        color: #FFF;
        text-align: center;
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 23px;
        /* 143.75% */
        letter-spacing: 0.071px;
        padding: 0 10px;
    }
}
</style>

  