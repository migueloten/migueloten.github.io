<template>
  <v-app>
    <v-main>
      <PortfolioPage />
    </v-main>
  </v-app>
</template>

<script>
import PortfolioPage from "./components/PortfolioPage.vue";

export default {
  name: "App",

  components: {
    PortfolioPage,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss">
@import "./assets/scss/variables.scss";
@import url("https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@100;200;300;400;600;700;800&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800;900&display=swap");

html,
body {
  background-color: $oxford-blue;
  font-family: "poppins", sans-serif;
}

#app {
  font-family: "poppins", sans-serif;
}

.v-application {
  background-color: $oxford-blue;
  color: $cultured;

  a {
    color: $sky-blue-crayola;
  }
}
</style>
