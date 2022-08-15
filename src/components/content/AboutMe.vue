<template>
  <v-container class="ma-0 pa-0">
    <div id="aboutMe" class="aboutMe">
      <div class="aboutMe__text">
        <h3>Olá, meu nome é</h3>
        <span>SEVERINO MIGUEL.</span>
        <h2>E eu gosto de criar aplicações para a web.</h2>
        <p>
          Ainda criança me tornei um entusiasta de tecnologia. Durante a
          graduação participei de eventos na área da programação e a curiosidade
          foi despertada. Logo comecei a desenvolver e acabei me interessando
          pelo front-end, então procurei experiências nesse campo e tenho
          buscado cada vez mais conhecimento nessa área.
        </p>
      </div>
      <div class="aboutMe__img mx-8 d-none d-md-flex">
        <v-img
          src="../../assets/perfil.png"
          width="400"
          aspect-ratio="1"
          cover
        ></v-img>
      </div>
    </div>
    <hr class="d-none d-md-flex" />
  </v-container>
</template>

<script>
export default {
  name: "AboutMe",
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.aboutMe {
  padding: 20px;
  padding-bottom: 0;
  margin-top: 200px;
  display: flex;

  &__text {
    margin-bottom: 20px;
    max-width: 650px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: flex-start;

    h3 {
      font-size: 20px;
    }

    span {
      font-size: 50px;
      color: $sky-blue-crayola;
    }

    p {
      text-align: justify;
    }
  }
}
</style>
