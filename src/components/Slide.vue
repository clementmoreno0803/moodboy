<template>
  <transition name="left">
    <div v-show="visibleSlide === index" class="slide">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  name: "Slide",
  props: ["visibleSlide", "index"],
  data() {
    return {};
  },
};
</script>

<style>
.slide {
  position: absolute ;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  width: 100vw;
  object-fit: cover;
}
.slide img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: relative;
}
.left-enter-active {
  animation: leafInAnimation 0.4s ease-in-out;
}
.left-leave-active {
  animation: leafOutAnimation 0.4s ease-in-out;
}
@keyframes leafInAnimation {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0);
  }
}
@keyframes leafOutAnimation {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-100%);
  }
}
</style>
