<script>
import { BaseTransition } from "vue";
import navbar from "./Components/navbar.vue";
import HomeSvg from "./assets/home.svg";
import AboutSvg from "./assets/about.svg";
import LearnSvg from "./assets/learn.svg";
import myherosection from "./Components/myherosection.vue";
export default {
  name: "app",
  components: {
    navbar,
    myherosection
  },
  data() {
    return {
      HomeSvg,
      AboutSvg,
      LearnSvg,
      navlinks: [
        { src: HomeSvg, text: "Home", href: "#Home" },
        { src: AboutSvg, text: "About", href: "#About" },
        { src: LearnSvg, text: "Learnmore", href: "#Learn" },
      ],
    };
  },
};
</script>

<template>
  <!-- this is my components for the navbar -->
  <navbar :links="navlinks" />
  <!-- this is for my hero section -->
  <myherosection :href="navlinks[0].href"/>
</template>

<style></style>
