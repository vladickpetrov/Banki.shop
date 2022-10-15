<template lang="">
  <header class="header">
    <div class="header__container">
      <ul class="header__links-container" v-if="windowWidth > 1280">
        <li class="header__link"><a>Каталог</a></li>
        <li class="header__link"><a>Доставка</a></li>
        <li class="header__link"><a>Оплата</a></li>
        <li class="header__link"><a>Контакты</a></li>
        <li class="header__link"><a>О компании</a></li>
      </ul>
      <button class="menu" v-if="windowWidth <= 1280"></button>
      <div class="search" v-if="windowWidth >= 525">
        <input class="search__input" placeholder="Поиск по названию картины" />
        <button class="search__button">Найти</button>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  data() {
    return {
      windowWidth: window.innerWidth,
    };
  },

  mounted() {
    this.$nextTick(() => {
      window.addEventListener("resize", this.onResize);
    });
  },

  beforeDestroy() {
    window.removeEventListener("resize", this.onResize);
  },

  methods: {
    onResize() {
      this.windowWidth = window.innerWidth;
    },
  },
};
</script>
<style scoped>
.menu {
  background-image: url(../images/Component1.svg);
  background-repeat: no-repeat;
  background-position: center;
  width: 48px;
  height: 48px;
  background-color: #403432;
  margin-left: 20px;
  border: 0;
}

.header {
  display: flex;
  justify-content: center;
  min-height: 97px;
  width: 100%;
  border-bottom: #e1e1e1 solid 1px;
}

.header__container {
  width: 1216px;
  display: flex;
  align-items: center;
}

.header__links-container {
  display: flex;
  padding-left: 96px;
}

.header__link {
  padding-left: 48px;
  font-size: 14px;
  font-weight: 400;
  line-height: 36px;
}

.header__link:first-child {
  padding-left: 0;
}

.search__input {
  background-color: #f6f3f3;
  height: 100%;
  width: 100%;
  border: 1px solid #e1e1e1;
  padding-left: 16px;
  transition: border 0.2s linear;
}

.search__input::placeholder {
  color: #9f9f9f;
}

.search__input:focus {
  border: 1px solid #b5b5b5;
}

.search__button {
  width: 122px;
  height: 100%;
  color: white;
  background-color: #403432;
  border: 0;
}

.search {
  display: flex;
  padding-left: 162px;
  width: 416px;
  height: 48px;
}

@media (max-width: 1280px) {
  .header__links-container {
    padding-left: 20px;
  }

  .header__container {
    justify-content: space-between;
  }

  .search {
    padding-right: 20px;
  }
}

@media (max-width: 680px) {
  .search {
    padding-left: 20px;
  }
}

@media (max-width: 525px) {
  .search__input {
    width: 200px;
  }
}
</style>
