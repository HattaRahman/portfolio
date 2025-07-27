<template>
  <div>
    <div class="overlay bg-[#0a0612] first"></div>
<div class="overlay bg-[#1a0d2e] second"></div>
<div class="overlay bg-purple-950 third"></div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'

onMounted(() => {
  gsap.to(".first", { delay: 0.5, duration: 1.5, top: "-100%", ease: "expo.inOut" })
  gsap.to(".second", { delay: 0.7, duration: 1.5, top: "-100%", ease: "expo.inOut" })
  gsap.to(".third", { delay: 0.9, duration: 1.5, top: "-100%", ease: "expo.inOut" })
})
</script>

<style scoped>
.overlay {
  @apply fixed top-0 left-0 w-full h-full z-[1000];
}
.first {
  left: 0%;
}
.second {
  left: 33.3%;
}
.third {
  left: 66.6%;
}
</style>
