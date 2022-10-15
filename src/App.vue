<template>
  <Header></Header>
  <main class="main">
    <Paintings :paintings="paintings"></Paintings>
  </main>
  <Footer></Footer>
</template>

<script>
import Header from "./components/Header.vue";
import Paintings from "./components/Paintings.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    Header,
    Paintings,
    Footer,
  },
  data() {
    return {
      paintings: [
        {
          title: "Рождение Венеры",
          author: "Сандро Боттичелли",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/0/0b/Sandro_Botticelli_-_La_nascita_di_Venere_-_Google_Art_Project_-_edited.jpg/640px-Sandro_Botticelli_-_La_nascita_di_Venere_-_Google_Art_Project_-_edited.jpg",
          price: 1000000,
          prevPrice: 2000000,
          isSold: false,
        },
        {
          title: "Тайная вечеря",
          author: "Леонардо да Винчи",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/The_Last_Supper_-_Leonardo_Da_Vinci_-_High_Resolution_32x16.jpg/640px-The_Last_Supper_-_Leonardo_Da_Vinci_-_High_Resolution_32x16.jpg",
          price: 3000000,
          isSold: false,
        },
        {
          title: "Сотворение Адама",
          author: "Микеланджело",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Michelangelo_-_Creation_of_Adam_%28cropped%29.jpg/640px-Michelangelo_-_Creation_of_Adam_%28cropped%29.jpg",
          price: 5000000,
          prevPrice: 6000000,
          isSold: false,
        },
        {
          title: "Урок анатомии",
          author: "Рембрандт",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Rembrandt_-_The_Anatomy_Lesson_of_Dr_Nicolaes_Tulp.jpg/637px-Rembrandt_-_The_Anatomy_Lesson_of_Dr_Nicolaes_Tulp.jpg",
          price: 10000000,
          isSold: true,
        },
      ],
    };
  },
};
</script>

<style>
@import url(./assets/main.css);

#app {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.main {
  min-height: 70vh;
  height: 100%;
  padding-top: 45px;
  max-width: 1216px;
}
</style>
