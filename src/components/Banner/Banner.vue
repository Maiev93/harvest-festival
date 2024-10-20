<template>
  <section class="banner">
    <BannerMain />
    <BannerSide />
  </section>
</template>

<script setup>
import BannerMain from './BannerMain.vue'
import BannerSide from './BannerSide.vue'

import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<style scoped>
.banner {
  position: relative;
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 24px;
}

@media screen and (max-width: 1023px) {
  .banner {
    grid-template: none;
  }
}

@media screen and (max-width: 768px) {
  .banner {
    gap: 0;
  }

  .banner-main::before {
    content: "";
    position: absolute;
    width: 98px;
    height: 99px;
    bottom: auto;
    left: auto;
    top: -55px;
    right: -55px;
    border-radius: 50%;
    border: 4px solid #dde0cd;
    background: transparent;
    z-index: 1;
  }

  .banner::after {
    content: "";
    position: absolute;
    width: 76px;
    height: 76px;
    top: 241px;
    left: -36px;
    border-radius: 50%;
    background: #6c846c;
  }
}
</style>
