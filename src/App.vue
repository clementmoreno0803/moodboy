<template>
  <nav>
    <img src="../src/assets/logo_mood.png" alt="" />
    <div class="description">
      <ul>
        <router-link to="/">Accueil,</router-link>
        <router-link to="/about">A propos,</router-link>
        <router-link to="/about">Mon travail,</router-link>
        <router-link to="/about">NFT,</router-link>
        <router-link to="/about">Vibes</router-link>
      </ul>
      <h2>Pour Connaisseurs & Curieux</h2>
    </div>
  </nav>
  <router-view />
  <Carousel @next="next" @previous="previous">
    <Slide
      v-for="(slide, index) in slides"
      :key="slide"
      :index="index"
      :visibleSlide="visibleSlide"
    >
      <img :src="slide" />
    </Slide>
  </Carousel>
</template>
<script>
import Carousel from '../src/components/Carousel.vue'
import Slide from '../src/components/Slide.vue'
export default {
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
  computed: {
    slideLeng(){
      return this.slides.length
    }
  },
  methods: {
    next(){
      if(this.visibleSlide >= this.slideLeng - 1){
        this.visibleSlide = 0
      }
      else{
        this.visibleSlide++
      }
    },
    previous(){
      if(this.visibleSlide <= 0){
        this.visibleSlide = this.slideLeng - 1
      }
      else{
        this.visibleSlide--
      }
    },
  }
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;700&display=swap");
:root {
  --main-font: "Open Sans";
  --main-color: black;
}
body {
  margin: 0;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  position: relative;
}

nav {
  padding: 10px 0;
  display: flex;
}
nav img {
  width: 75px;
  height: 75px;
  padding-left: 20px;
}
nav a {
  color: var(--main-color);
  font-size: 1.5em;
  text-decoration: none;
  padding: 0 2px;
  text-align: left;
  text-transform: uppercase;
  font-family: var(--main-font);
  font-weight: 400;
}

nav a.router-link-exact-active {
  border-bottom: 1px solid black;
}
.description {
  padding-left: 20px;
}
ul {
  margin: 0;
  padding: 0;
  text-align: left;
}
h2 {
  font-size: 2.5em;
  text-align: left;
  margin: 0;
  font-family: var(--main-font);
  font-weight: 400;
  line-height: 1.15;
}
</style>
