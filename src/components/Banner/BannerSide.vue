<template>
  <div class="banner-side">
    <picture class="banner-side__picture">
      <source
        media="(min-width: 769px)"
        srcset="../../assets/images/banner-small.png"
      />
      <img
        class="banner-side__image"
        src="../../assets/images/banner-small-mobile.png"
        alt="Выставка тыкв"
      />
    </picture>
    <div class="banner-side__content content">
      <p class="content_up">А также:</p>
      <h2 class="content__header">Выставка тыкв</h2>
      <p class="content_down text">
        <span class="text_tight"
          >Местные фермеры покажут свои самые большие тыквы.</span
        >
        <span class="text_wide"
          >Посоревнуются чья тыква тяжелее и&nbsp;крепче.</span
        >
      </p>
    </div>

    <button class="banner-side__button">ещё о выставке</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<style scoped>
.banner-side {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 45px;
  min-width: 260px;
  padding: 12%;
}

.banner-side::before {
  content: "";
  position: absolute;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  z-index: -1;
  background-color: #567057;
  border-radius: 10px;
}

.banner-side::after {
  content: "";
  position: absolute;
  top: clamp(-3rem, -2.3333rem - 1.0417vw, -4rem);
  right: clamp(-3rem, -2.3333rem - 1.0417vw, -4rem);
  width: clamp(6.25rem, 0.4167rem + 9.1146vw, 15rem);
  height: clamp(6.25rem, 0.4167rem + 9.1146vw, 15rem);
  border-radius: 50%;
  border: clamp(0.25rem, 0.1667rem + 0.1302vw, 0.375rem) solid #dde0cd;
  background: transparent;
}

.banner-side__picture {
  position: absolute;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  z-index: -1;
  width: 100%;
  height: 100%;
}

.banner-side__image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 10px;
}

.banner-side__button {
  padding: clamp(1rem, -0.3333rem + 2.0833vw, 3rem);
  font-size: clamp(1rem, -0.3333rem + 2.0833vw, 3rem);
  letter-spacing: 0.05em;
  text-transform: uppercase;
  color: #fff;
  background-color: transparent;
  border: 2px solid #fff;
  border-radius: 10px;
}

.banner-side__button:hover {
  cursor: pointer;
  box-shadow: 0px 0px 2px 1px #fff;
}

.content {
  display: grid;
  gap: 11px;
}

.content_up {
  font-size: clamp(2rem, 0rem + 3.125vw, 5rem);
  line-height: clamp(2.25rem, -0.9167rem + 4.9479vw, 7rem);
  color: #fff;
}

.content__header {
  max-width: 80%;
  font-size: clamp(2rem, 0rem + 3.125vw, 5rem);
  font-weight: 700;
  line-height: clamp(2rem, 0rem + 3.125vw, 5rem);
  color: #fff;
}

.content_down {
  font-size: clamp(1rem, -0.3333rem + 2.0833vw, 3rem);
  line-height: clamp(1.5rem, -0.1667rem + 2.6042vw, 4rem);
  color: #fff;
}

.text_tight {
  display: inline-block;
  padding-right: 23%;
}

@media screen and (max-width: 768px) {
  .banner-side {
    gap: 27px;
    padding: 10px 20px 20px 20px;
    border-radius: 0 0 10px 10px;
  }

  .banner-side::after {
    content: "";
    position: absolute;
    width: 35px;
    height: 36px;
    top: auto;
    right: auto;
    left: 46px;
    bottom: -16px;
    border: none;
    border-radius: 50%;
    background: #183022;
    z-index: -2;
  }

  .banner-side__picture::after {
    content: "";
    position: absolute;
    width: 35px;
    height: 36px;
    top: -18px;
    right: 18px;
    border-radius: 50%;
    background: #bcccaf;
  }

  .banner-side__image {
    border-radius: 0 0 10px 10px;
  }

  .content {
    gap: 8px;
  }

  .content_up {
    font-size: 20px;
    font-weight: 400;
    line-height: 24.2px;
  }

  .content__header {
    font-size: 20px;
    font-weight: 700;
    line-height: 20px;
  }

  .content_down {
    display: none;
  }
}
</style>
