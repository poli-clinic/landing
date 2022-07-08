<template>
  <carousel :items-to-show="1" :autoplay="200000" :wrap-around="true">
    <slide v-for="slide in slides" :key="slide">
      <div class="carousel__item">
        <img ref="bg-slide" alt="{{ slide.title }}" title="{{ slide.title }}" :src="slide.image">
        <div class="carousel-item__content">
          <Typography :heading="1">{{ slide.title }}</Typography>
          {{ slide.excerpt }}
        </div>
      </div>
    </slide>
    <template #addons>
      <navigation/>
    </template>
  </carousel>
</template>

<script>
// If you are using PurgeCSS, make sure to whitelist the carousel CSS classes
import {ref} from 'vue';
/*! purgecss start ignore */
import 'vue3-carousel/dist/carousel.css';
/*! purgecss end ignore */
import Typography from "@/components/Typography";
import {Carousel, Slide, Navigation} from 'vue3-carousel';


export default {
  name: 'App',
  components: {
    Carousel,
    Slide,
    Navigation,
    Typography
  },
  setup() {
    // make users variable reactive with the ref() function
    const slides = ref([
      {
        title: 'Title 1',
        excerpt: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
        image: 'https://ik.imagekit.io/vj78ie3kf/image1_581IvtKOl.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1657289646337'
      },
      {
        title: 'Title 2',
        excerpt: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
        image: 'https://ik.imagekit.io/vj78ie3kf/image2_tngLQ4G23.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1657289646332'
      },
      {
        title: 'Title 3',
        excerpt: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
        image: 'https://ik.imagekit.io/vj78ie3kf/image1_581IvtKOl.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1657289646337'
      },
      {
        title: 'Title 4',
        excerpt: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
        image: 'https://ik.imagekit.io/vj78ie3kf/image2_tngLQ4G23.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1657289646332'
      },
      {
        title: 'Title 5',
        excerpt: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
        image: 'https://ik.imagekit.io/vj78ie3kf/image1_581IvtKOl.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1657289646337'
      }
    ]);

    return {
      slides
    };
  }
};
</script>

<style lang="scss">
/* purgecss start ignore */
.carousel__prev, .carousel__next {
  top: 0;
  transform: none;
  height: 100%;
  border-radius: 0;
  background-color: transparent;
  width: 50%;
  max-width: 220px;
  transition: all .5s linear;
  .carousel__icon{
    opacity: 0;
    transition: all .5s linear;
    width: 2rem;
    height: 2rem;
  }
  &:hover{
    background-color: rgba(0, 0, 0, .4);
    .carousel__icon{
      opacity: 1;
    }
  }
}

.carousel__item {
  height: 0;
  padding-bottom: 45%;
  width: 100%;
  color: var(--vc-clr-white);
  font-size: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  img {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
    top: 0;
    left: 0;
  }
}

.carousel-item__content {
  position: absolute;
  z-index: 2;
  max-width: 600px;
  width: 100%;
  bottom: 40px;
}

@media (max-width: 767px){
  .carousel__item {
    padding-bottom: 120%;
  }
}
/* purgecss end ignore */
</style>