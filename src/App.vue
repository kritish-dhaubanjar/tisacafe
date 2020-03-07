<template>
  <div id="app">
    <div v-if="false">
      <Drinks />
    </div>

    <div v-else>
      <transition enter-active-class="animated fadeIn" leave-active-class="animated fadeOut">
        <Slide @hideMenu="hideMenu" v-if="show" />
      </transition>
      <Header @showMenu="show = true" />
      <Carousel />
      <div id="background">
        <About />
        <Menu />
      </div>
      <Map />
      <Footer />
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header";
import Slide from "@/components/Slide";
import Carousel from "@/components/Carousel";
import About from "@/components/About";
import Menu from "@/components/Menu";
import Footer from "@/components/Footer";
import Map from "@/components/Map";
import Drinks from "@/components/menu/Drinks";

export default {
  name: "App",
  data() {
    return {
      show: false
    };
  },

  methods: {
    hideMenu() {
      document.body.classList = [];
      this.show = false;
    }
  },

  components: {
    Header,
    Carousel,
    About,
    Menu,
    Footer,
    Slide,
    Map,
    Drinks
  }
};
</script>

<style lang="scss">
@import "~@/colors.scss";
#app {
  font-family: "Montserrat";
  font-size: 16px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

button,
.btn {
  border-radius: 0 !important;
  font-family: "Montserrat";
  font-size: 13px;
}

.btn-primary {
  background-color: transparent;
  border-color: $primary;
  color: $primary;
  font-weight: 600;
  padding: 8px 16px;
  &:hover,
  &:active,
  &:focus {
    background-color: $primary !important;
    color: #fff !important;
    border-color: $primary !important;
    box-shadow: none !important;
  }
}

h1,
h3,
h4,
h6 {
  font-family: "Bellefair";
}

.card {
  border-radius: 0 !important;
}

@media screen and (max-width: 1199px) {
  .container {
    max-width: 100%;
  }
}

body.noscroll {
  overflow: hidden !important;
}

.map {
  line-height: 0 !important;
}

#background {
  color: #fff;
  background-image: url("./assets/background.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  background-attachment: fixed;
}
</style>
