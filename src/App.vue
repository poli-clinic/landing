<template>
  <div id="fancy-page">
    <CarouselVue></CarouselVue>

    <div class="container">
      <div class="row py-7">
        TEST
        <Grid :col="4">
          <Card :img="'green_socks'" :title="'Title card'" :msg="'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor'"></Card>
        </Grid>
        <Grid :col="4">
          <Card :img="'azure_socks'" :title="'Title card'" :msg="'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor'"></Card>
        </Grid>
        <Grid :col="4">
          <Card :img="'red_socks'" :title="'Title card'" :msg="'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor'"></Card>
        </Grid>
      </div>

      <div class="flex flex-column--mobile py-7" data-animation>
        <img ref="logo" :src="logoImg" alt="Logo" width="210" height="210">

        <Circle :color="colors.blue" />
        <Circle :color="colors.red" />
        <Circle :color="colors.yellow" />
        <Circle :color="colors.green" />
        <Circle :color="colors.purple" />
        <Circle :color="colors.pink" />
      </div>

    </div>

    <Footer></Footer>

  </div>
</template>

<script setup>
import {ref,onMounted} from "vue";
import gsap from 'gsap';
import ScrollTrigger from "gsap/ScrollTrigger";
// @ts-ignore
import logoImg from './assets/logo.png';
import Circle from "./components/Circle.vue";
import CarouselVue from "./components/Carousel.vue";
import Card from "./components/Card.vue";
import Grid from "./components/Grid.vue";
import Footer from "./components/Footer.vue";


const logo = ref(null);
let tl = null;

const colors = {
  brand: '#42b983',
  blue: '#0277bd',
  red: '#c62828',
  yellow: '#ffeb3b',
  purple: '#6a1b9a',
  green: '#43a047',
  pink: '#ff80ab',
}

onMounted(() => {

  gsap.registerPlugin(ScrollTrigger);

  tl = gsap.timeline({
    scrollTrigger: {
      trigger: "[data-animation]",
      //markers: true
    }
  });

  tl.from(logo.value, {
    x: -300,
    backgroundColor: colors.yellow,
    border: `5px solid ${colors.pink}`,
    duration: 3,
    rotation: 40,
    ease: "bounce",
  });

  tl.from(
      ".circle",
      {
        y: "random(-200, 200)",
        opacity: 0,
        duration: 1,
        stagger: 0.15,
      },
      "+=1"
  );
});

</script>

<style scoped lang="scss">
#fancy-page {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  padding: 0 1rem;
  h1 {
    font-size: 4rem;
  }
  img {
    border-radius: 100%;
  }
  *, ::after, ::before {
    box-sizing: border-box;
  }
}

.py-7{
  padding-top: 7rem;
  padding-bottom: 7rem;
}

.flex{
  display: flex;
  align-items: center;
  justify-content: center;
}

.container{
  width: 100%;
  padding-left: 1rem;
  padding-right: 1rem;
  display: block;
}

.row{
  display: flex;
  flex-wrap: wrap;
  margin-left: -1rem;
  margin-right: -1rem;
}

@media (max-width: 767px) {
  .flex-column--mobile{
    flex-direction: column;
  }
}
</style>
