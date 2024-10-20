<template>
  <div class="cards">
    <h5 class="cards__title">Что на прилавке</h5>
    <div class="cards__content">
      <Card v-for="card in cards" :key="card.id" :card="card" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Card from './Card.vue'

const cards = ref([
  {
    id: '1',
    image: 'item1.png',
    url: '#',
    title: 'Тыква',
    price: '500'
  },
  {
    id: '2',
    image: 'item2.png',
    url: '#',
    title: 'Цветная капуста',
    price: '350'
  },
  {
    id: '3',
    image: 'item3.png',
    url: '#',
    title: 'Мята',
    price: '150'
  },
  {
    id: '4',
    image: 'item4.png',
    url: '#',
    title: 'Базилик',
    price: '450'
  },
  {
    id: '5',
    image: 'item5.png',
    url: '#',
    title: 'Кабачок',
    price: '50'
  }
])
</script>

<style scoped>
.cards {
  position: relative;
}

.cards::before {
  content: "";
  position: absolute;
  bottom: 11%;
  right: 1.25%;
  width: 5%;
  height: 12%;
  border-radius: 50%;
  background: #afb982;
}

.cards::after {
  content: "";
  position: absolute;
  z-index: -1;
  bottom: 40%;
  left: 16%;
  width: 4%;
  height: 11%;
  border-radius: 50%;
  background: #183022;
}

.cards__title {
  margin: 5.5% 0 2.75% 0;
  font-size: clamp(2.5rem, -0.4167rem + 4.5573vw, 6.875rem);
  font-weight: 700;
  color: #183022;
}

.cards__content {
  display: flex;
  justify-content: space-between;
  gap: clamp(1.4375rem, 0.3125rem + 1.7578vw, 3.125rem);
  padding-bottom: 5%;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  scroll-snap-align: start;
}

@media screen and (max-width: 768px) {
  .cards::before {
    content: "";
    position: absolute;
    bottom: 4px;
    right: 12%;
    width: 46px;
    height: 46px;
    border-radius: 50%;
    background: #afb982;
  }

  .cards::after {
    display: none;
  }

  .cards__title {
    margin: 35px 0 24px 10px;
    font-size: 30px;
    font-weight: 700;
    line-height: 40px;
  }

  .cards__content {
    gap: 10px;
  }
}
</style>
