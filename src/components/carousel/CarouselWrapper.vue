<template>
    <Carousel :wrap-around="true" :breakpoints="breakpoints">
      <Slide v-for="(slide, index) in items" :key="index">
        <img :src="slide.imgUrl" />
      </Slide>
  
      <template #addons>
        <Navigation>
          <template #next>
            <img src="/ar.svg" />
          </template>
          <template #prev>
            <img src="/al.svg" />
          </template>
        </Navigation>
      </template>
    </Carousel>
  </template>
    
  <script lang="ts">
  import { defineComponent, PropType } from 'vue'; // Import defineProps
  import { Carousel, Navigation, Slide } from 'vue3-carousel';
  import 'vue3-carousel/dist/carousel.css';
  
  interface Item {
    imgUrl?: string;
  }
  

  
  export default defineComponent({
    components: {
      Carousel,
      Navigation,
      Slide
    },
    props: {
      items: {
        type: Array as PropType<Item[]>,
        required: true
      }
    },
    data() {
      return {
        breakpoints: {
          350: {
            itemsToShow: 1,
            snapAlign: 'center'
          },
          1024: {
            itemsToShow: 2,
            snapAlign: 'center'
          },
          1280: {
            itemsToShow: 2,
            snapAlign: 'center'
          }
        }
      };
    }
  });
  </script>
  
  <style>
  /* Your styles here */
  </style>
  

<style>
:root {}

.carousel__item {
    min-height: 200px;
    width: 100%;
    color: var(--vc-clr-white);
    font-size: 20px;
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.carousel__slide {
    padding: 10px;

    &>img {
        width: 735px;
        height: 435px;
        width: 100%;
        object-fit:cover;
        border-radius: 10px;
    }
}

.carousel__prev,
.carousel__next {
    box-sizing: content-box;
    top: unset;
    bottom: 0;
    transform: translateY(74px);
    width: 40px;
    height: 43px;
}

.carousel__prev {
    left: 40%;
}

.carousel__next {
    right: calc(40% - 60px);
}
</style>

  