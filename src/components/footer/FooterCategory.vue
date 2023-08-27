<template>
    <div class="footer-category">
        <h6 class="category-title">
            {{ footerCategory.title }}
        </h6>
        <a class="footer-link" v-for="footerItem in footerCategory.footerItems" href="#">{{ footerItem }}</a>
    </div>
</template>
    
<script lang="ts">
import { defineComponent, PropType } from 'vue';


interface FooterCategory {
    title: string;
    footerItems: string[];
}



export default defineComponent({
    props: {
        footerCategory: {
            type: Object as PropType<FooterCategory>,
            required: true
        }
    },

});
</script>
  


<style>
.footer-category {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-width:350px;

    &>.category-title {
        text-transform: uppercase;
        color: #FFF;
        text-align: center;
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 36px;
        letter-spacing: 0.08px;
    }

    &>.footer-link {
        text-decoration: none;
        color: #FFF;
        text-align: center;
        font-size: 16px;
        font-style: normal;
        font-weight: 700;
        line-height: 36px;
        letter-spacing: 0.08px;
    }
}
</style>

  