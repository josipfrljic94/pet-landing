<template>
  <HomeBanner />
  <Title title="Daily pet facts - Love!" :isMain="true" />
  <InfoBlock title="The cat" imgUrl="/meow.png" :imgLeft="true" :hasGutter="true">
    <span>
      Cats have been domesticated for around 4,000 years. While they were once valued for their hunting abilities, they
      are
      now valued for their companionship and loving behaviour.

      <br />
      <br />

      While not well known, the collective nouns used for cats and kittens are a clowder of cats and a kindle of
      kittens.

      <br />
      Our domestic cats are known as little cats. They differ from large cats such as lions and tigers because they
      are
      naturally active at night and can purr.
      <br />
      <br />

      Cats are now the most popular pet in the UK and in the US.</span>
  </InfoBlock>

  <InfoBlock title="The cat" imgUrl="/woof.png" :imgLeft="false">
    <span>
      Domestic dogs have been companions to people for more than 15,000 years. There are more than 400 different breeds of
      dogs. PAWS or your local animal shelter has a wide variety of breeds available for adoption. The most popular types
      are the non-pedigree. They are extra special because they are one-of-a-kind!
      <br />
      <br />

      In general, small dogs live longer than large dogs. Small dogs such as terriers may live 20 years. Giant dogs like
      Great Danes may live eight years. The average lifespan for a mixed breed dog is 13 to 14 years. By making sure dogs
      have good food, regular veterinary care, shelter and a loving family, they will live longer, healthier lives.
    </span>
  </InfoBlock>
  <div class="light-wrapper">
    <Title :isMain="false" title="Gallery" />
    <CarouselWrapper :items="carouselItems" />
    <Grid :images="gridItems" />
  </div>
  <CookieBanner />
  <Footer :footerCategories="footerData" />
</template>

<script setup lang="ts">
import HomeBanner from './components/home_banner/HomeBanner.vue';
import Title from "./components/title/Title.vue";
import InfoBlock from "./components/info_block/InfoBlock.vue";
import CarouselWrapper from "./components/carousel/CarouselWrapper.vue";
import Grid from "./components/grid/Grid.vue";
import Footer from "./components/footer/Footer.vue";
import CookieBanner from "./components/cookie-banner/CookieBanner.vue";
import { defineComponent } from 'vue';

const carouselItems = [
  { imgUrl: '/slider.png' },
  { imgUrl: '/meow.png' },
  { imgUrl: '/meow.png' },
]

const gridItems = [
  {
    imgUrl: "/img_1.png",
  },
  {
    imgUrl: "/img_2.png",
  },
  {
    imgUrl: "/img_3.png",
  },
  {
    imgUrl: "/img_4.png",
  },
  {
    imgUrl: "/img_5.png",
  },
  {
    imgUrl: "/img_6.png",
  },
  {
    imgUrl: "/img_7.png",
  },
  {
    imgUrl: "/img_8.png",
  },
];

const footerData = [
  {
    title: "pet-facts.com",
    footerItems: [
      "About us",
      "Careers",
      "FAQ"
    ]
  },
  {
    title: "pet-facts.com",
    footerItems: [
      "About us",
      "Careers",
      "FAQ"
    ]
  },
  {
    title: "pet-facts.com",
    footerItems: [
      "About us",
      "Careers",
      "FAQ"
    ]
  }
]


defineComponent({
  components: { CarouselWrapper },
})
// console.log(this)
</script>


<style scoped>
.light-wrapper {
  background-color: #fff;
  box-shadow: 0 0 0 100vmax #fff;
  clip-path: inset(0 -100vmax);
}
</style>
