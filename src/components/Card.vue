<template>

  <div class="card">
    <div class="card-image"
         data-aos="fade-up"
         data-aos-offset=""
         data-aos-easing="ease-in-out"
    >
      <BaseIcon :name="img"></BaseIcon>
    </div>
    <div class="card-header">
      <Typography :heading="2"
        data-aos="fade-up"
        data-aos-offset=""
        data-aos-easing="ease-in-out">
        {{ title }}
      </Typography>
    </div>
    <div class="card-body">
      <p 
        data-aos="zoom-in"
        data-aos-offset=""
        data-aos-easing="ease-in-out">
        {{msg}}
    </p>
    </div>
  </div>

</template>

<script>
import { onMounted } from "@vue/runtime-core";
import Typography from "./Typography.vue";
import BaseIcon from "./BaseIcon.vue";
import AOS from 'aos';
import 'aos/dist/aos.css'

export default {
  name: "Card",
  props: {
    msg: String,
    title: String,
    img: String
  },
  components: {Typography, BaseIcon},
  setup() {
    onMounted(() => {
      console.log('aos')
      AOS.init();
    });
  },
};

</script>