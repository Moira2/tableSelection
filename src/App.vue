<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <TableSelection></TableSelection> -->
    <!-- <popupComp></popupComp> -->
    <!-- <gradientFont></gradientFont> -->
    <!-- <awesome-swiper></awesome-swiper> -->
    <new-carousel> </new-carousel>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import TableSelection from './components/tableSelection.vue'
// import popupComp from "./components/popupComp.vue";
// import gradientFont from "./components/gradientFont.vue"
// import awesomeSwiper from "./components/awesomeSwiper.vue";
import newCarousel from "./components/newCarousel.vue";

export default {
  name: "App",
  components: {
    // HelloWorld
    // TableSelection,
    // popupComp,
    // gradientFont,
    // awesomeSwiper,
    newCarousel,
  },
};
</script>

<style>
html {
  height: 100%;
  width: 100%;
}
a {
  text-decoration: none;
}
li {
  list-style: none;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
