<template>
  <div class="content d-flex">
    <div class="content__base d-flex">
      <about-me />
    </div>
    <div class="d-none d-md-flex content__aside">
      <a href="https://www.linkedin.com/in/severino-miguel/" target="_blank"
        ><v-icon>mdi-linkedin</v-icon></a
      >
      <a href="https://github.com/migueloten" target="_blank"
        ><v-icon>mdi-github</v-icon></a
      >
      <a href="https://wa.me/5584998014877" target="_blank"
        ><v-icon>mdi-whatsapp</v-icon></a
      >
      <a href="https://twitter.com/migueloten1" target="_blank"
        ><v-icon>mdi-twitter</v-icon></a
      >
      <a href="https://www.instagram.com/miguel_neto1/" target="_blank"
        ><v-icon>mdi-instagram</v-icon></a
      >
      <a
        href="https://drive.google.com/file/d/1Ap3X6evJR_IUK0Jlhzczs8_TMXbLGOuf/view?usp=sharing"
        target="_blank"
        ><v-icon>mdi-file-account</v-icon></a
      >
    </div>
  </div>
</template>

<script>
import AboutMe from "./content/AboutMe.vue";
export default {
  name: "PortfolioPage",
  components: { AboutMe },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/variables.scss";

.content {
  justify-content: space-evenly;

  &__aside {
    position: fixed;
    bottom: 25px;
    right: 35px;
    flex-direction: column;
    flex-wrap: nowrap;
    align-items: center;
    align-content: center;
    justify-content: center;

    a {
      text-decoration: none;
      color: $cultured;

      &:hover {
        color: $sky-blue-crayola;
      }

      .v-icon {
        margin-top: 25px;
      }
    }
  }
}
</style>
