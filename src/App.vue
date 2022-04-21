<template class="app">
  <Hero />
  <Portfolio />
</template>

<script>
import Hero from "./components/hero.vue";
import Portfolio from "./components/portfolio.vue";
export default {
  components: {
    Portfolio,
    Hero,
  },

  data() {},
};
</script>

<style scoped></style>
