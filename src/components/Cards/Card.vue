<template>
  <a class="card" :href="card.url">
    <img class="card__image" :src="getImageUrl()" :alt="card.title" />
    <div class="card__content">
      <p class="card__title">
        {{ card.title }}
      </p>
      <p class="card__price">{{ card.price }} ₽</p>
    </div>
  </a>
</template>

<script setup>
const props = defineProps({
  card: Object
})


function getImageUrl() {
  return new URL(`../../assets/images/${props.card.image}`, import.meta.url)
}
</script>

<style scoped>
.card {
  display: inline-block;
  text-decoration: none;
  background: #fff;
  box-shadow: 0px 10px 10px 0px #00000012;
  border-radius: 10px;
  scroll-snap-align: start;
  width: clamp(10.125rem, -1.0417rem + 17.4479vw, 26.875rem);
  aspect-ratio: 1.6 / 1.2;
  flex-grow: 1;
}

.card__image {
  width: 100%;
  border-radius: 10px;
  object-fit: cover;
}

.card__content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 100%;
  height: 100%;
  gap: 12px;
  padding: 6.5% 12% 19% 12%;
}

.card__title {
  padding-right: 10%;
  font-size: clamp(1rem, -0.3333rem + 2.0833vw, 3rem);
  color: #485f3b;
}

.card__price {
  font-size: clamp(1rem, -0.3333rem + 2.0833vw, 3rem);
  font-weight: 700;
  color: #485f3b;
}

@media screen and (max-width: 768px) {
  .card {
    display: flex;
    flex-direction: column;
   min-width: 40%;
        min-height: 260px;
        aspect-ratio: 0;
  }

  .card__content {
    flex-grow: 1;
    height: auto;
    padding: 10px 10px 14px 16px;
  }
}
</style>
