<template>
  <div class="banner-main">
    <picture class="banner-main__picture">
      <source
        media="(min-width: 769px)"
        srcset="../../assets/images/banner.png"
      />
      <img
        class="banner-main__image"
        src="../../assets/images/banner-mobile.png"
        alt="Фестиваль фермерских товаров"
      />
    </picture>
    <p class="banner-main__date">20-22 сентября</p>
    <div class="banner-main__header">
      <h1 class="banner-main__title">Фестиваль фермерских товаров</h1>
      <a href="#" class="banner-main__link">
        <img
          class="banner-main__icon"
          src="../../assets/icons/arrow.svg"
          alt="Фестиваль фермерских товаров"
          width="60px"
        />
      </a>
    </div>
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
.banner-main {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-width: 38.75rem;
  min-height: 25rem;
  padding: 6% 5%;
  /* aspect-ratio: 3.1 / 2; */
  border-radius: 10px;
  background: linear-gradient(
    180deg,
    rgba(173, 180, 148, 0) 29.5%,
    #aeb595 100%
  );
}

.banner-main::before {
  content: "";
  position: absolute;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  z-index: -1;
  border-radius: 10px;
  background-color: #aeb595;
}

.banner-main::after {
  content: "";
  position: absolute;
  bottom: 33%;
  left: -6%;
  width: clamp(4.75rem, -2.5rem + 11.3281vw, 15.625rem);
  height: clamp(4.75rem, -2.5rem + 11.3281vw, 15.625rem);
  border-radius: 50%;
  background: #6c846c;
}

.banner-main__picture {
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  width: 100%;
  height: 100%;
}

.banner-main__image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 10px;
}

.banner-main__date {
  font-size: clamp(2rem, 0rem + 3.125vw, 5rem);
  color: #fff;
}

.banner-main__header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  gap: 90px;
}

.banner-main__header::before {
  content: "";
  position: absolute;
  bottom: -2%;
  right: 15.5%;
  width: clamp(2.25rem, 0rem + 3.5156vw, 5.625rem);
  height: clamp(2.25rem, 0rem + 3.5156vw, 5.625rem);
  border-radius: 50%;
  background: #bcccaf; 
  z-index: -1;
}

.banner-main__title {
  font-size: clamp(2.5rem, 0.1667rem + 3.6458vw, 6rem);
  font-weight: 700;
  color: #fff;
  min-width: 415px;
  z-index: 1;
}

.banner-main__link {
  display: block;
  width: clamp(5rem, 2.3333rem + 4.1667vw, 9rem);
  aspect-ratio: 3 / 2;
}

.banner-main__icon {
  width: -webkit-fill-available;
}

@media screen and (max-width: 768px) {
  .banner-main {
    overflow: hidden;
    justify-content: flex-start;
    gap: 10px;
    min-width: 300px;
    min-height: 400px;
    padding: 20px;
    aspect-ratio: auto;
    border-radius: 10px 10px 0 0;
    background: none;
  }

  .banner-main::after {
    content: none;
  }

  .banner-main__image {
    border-radius: 10px 10px 0 0;
  }

  .banner-main__date {
    font-size: 20px;
    font-weight: 400;
    line-height: 24.2px;
  }

  .banner-main__header {
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    gap: 24px;
  }

  .banner-main__header::before {
    content: none;
  }

  .banner-main__title {
    min-width: 219px;
    font-size: 30px;
    font-weight: 700;
    line-height: 30px;
  }

  .banner-main__link {
    width: 60px;
  }
}
</style>
