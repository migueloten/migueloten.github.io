<template>
  <v-container class="ma-0 pa-0">
    <header-page />
    <portfolio-content />
  </v-container>
</template>

<script>
import HeaderPage from "./HeaderPage.vue";
import PortfolioContent from "./PortfolioContent.vue";

export default {
  components: { HeaderPage, PortfolioContent },
  name: "PortfolioPage",

  data: () => ({}),
};
</script>

<style lang="scss" scoped>
.v-container {
  max-width: 100%;
}
</style>
