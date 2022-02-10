<template>
  <div class="caroussel">
    <slot></slot>
    <img
      src="../assets/previous.png"
      alt=""
      class="previous"
      @click="previous"
    />
    <img src="../assets/logo_mood.png" alt="" class="next" @click="next" />
  </div>
</template>

<script>
export default {
  name: "Carousel",
  methods: {
    next() {
      this.$emit("next");
    },
    previous() {
      this.$emit("previous");
    },
  },
};
</script>

<style>
.caroussel {
  position: relative;
  overflow: hidden;
  height: calc(100vh - 100px);
}
.previous {
  position: absolute;
  bottom: 50px;
  right: 120px;
  width: 75px;
  height: 75px;
}
.previous.active {
  transform: rotate(20deg);
  transition: all 0.5s ease;
}
.next {
  position: absolute;
  bottom: 50px;
  right: 25px;
  width: 75px;
  height: 75px;
}
</style>
