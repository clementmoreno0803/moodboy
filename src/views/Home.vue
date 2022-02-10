<template>
    <Carousel>
    <Slide v-for="(slide,index) in slides" :key="slide" :index="index" :visibleSlide="visibleSlide">
      <img :src="slide">
    </Slide>
  </Carousel>
</template>

<script>
// @ is an alias to /src
import Carousel from '../src/components/Carousel.vue'
import Slide from '../src/components/Slide.vue'

export default {
  name: 'Home',
  data() {
    return {
      slides: [
        "https://images.unsplash.com/photo-1481349518771-20055b2a7b24?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8",
        "https://images.unsplash.com/photo-1509281373149-e957c6296406?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=100&q=80",
        "https://images.unsplash.com/photo-1509114397022-ed747cca3f65?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=100&q=80"
      ],
      visibleSlide: 0,
    };
  },
  components: {
    Carousel,
    Slide,
  },
};
</script>
