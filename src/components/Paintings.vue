<template lang="">
  <div class="paintings">
    <h1 class="paintings__header">Картины эпохи Возрождения</h1>
    <ul class="paintings__container">
      <li class="item" v-for="p in paintings">
        <img class="item__image" :src="p.image" />
        <h2 class="item__title">«{{ p.title }}» <br />{{ p.author }}</h2>
        <div class="price">
          <div class="price__container">
            <h6 class="price__previous-price" v-if="p.prevPrice">
              {{ p.prevPrice.toLocaleString("ru-RU") }} $
            </h6>
            <h3 class="price__current-price">
              {{ p.price.toLocaleString("ru-RU") }} $
            </h3>
          </div>
          <button class="price__buy-button">Купить</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    paintings: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.paintings__header {
  padding-bottom: 39px;
}

.paintings__container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 32px;
  padding-bottom: 30px;
}

.price__buy-button {
  width: 118px;
  height: 48;
  color: white;
  background-color: #403432;
  border: 0;
  margin-right: 24px;
}

.item {
  width: 280px;
  height: 328px;
  display: flex;
  flex-direction: column;
  border: #e7e7e7 1px solid;
}

.item__image {
  width: 280px;
  height: 160px;
  object-fit: cover;
  object-position: left;
  border-bottom: #e7e7e7 1px solid;
}

.item__title {
  line-height: 27px;
  padding-left: 24px;
  padding-top: 20px;
}

.price {
  display: flex;
  padding-top: 22px;
  justify-content: space-between;
  justify-self: end;
  height: 48px;
}

.price__container {
  padding-left: 24px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.price__previous-price {
  text-decoration-line: line-through;
  color: #a0a0a0;
  line-height: 21px;
}

.price__current-price {
  line-height: 24px;
}

@media (max-width: 1280px) {
  .paintings__container {
    grid-template-columns: repeat(3, 1fr);
    gap: 32px;
  }
}

@media (max-width: 920px) {
  .paintings__container {
    grid-template-columns: repeat(2, 1fr);
    gap: 32px;
  }
}

@media (max-width: 620px) {
  .paintings__container {
    grid-template-columns: repeat(1, 1fr);
    gap: 32px;
    justify-items: center;
  }
}

@media (max-width: 430px) {
  .paintings__header {
    padding-left: 20px;
  }
}
</style>
