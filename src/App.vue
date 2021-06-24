<template>
  <div id="app">
    <Navbar />
    <Home />
    <go-top />
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar/Navbar.vue";
import Home from "./views/Home.vue";
import Footer from "./components/Footer/Footer.vue";
import goTop from "./components/global/goTop.vue"

export default {
  name: "App",
  components: {
    Home,
    Navbar,
    Footer,
    goTop
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Lato", sans-serif;
}
</style>
