<template>
  <v-container id="tab-resume" class="ma-0 pa-0">
    <v-container id="resumeCv" class="resumeCv">
      <v-tabs v-model="tab" :direction="windowWidth">
        <v-tab value="education">Educação</v-tab>
        <v-tab value="experience">Experiências</v-tab>
        <v-tab value="skills">Habilidades</v-tab>
      </v-tabs>
      <v-window v-model="tab" class="resumeCv__content">
        <v-window-item value="education">
          <h2>Educação</h2>
          <div class="resumeCard pl-4">
            <h3>
              <v-icon>mdi-school</v-icon> Universidade Federal do Rio Grande do
              Norte - UFRN
            </h3>
            <p>2017 - 2021</p>
            <p class="mt-4">
              Bacharelado em Ciências e Tecnologia - Ênfase em Tecnologia da
              Computação
            </p>
          </div>
          <div class="resumeCard pl-4">
            <h3>
              <v-icon>mdi-school</v-icon> Intituto Metrópole Digital UFRN - IMD
            </h3>
            <p>2022 - 2023</p>
            <p class="mt-4">
              Técnicom em Tecnologia da Informação - Ênfase em Informática para
              Internet
            </p>
          </div>
        </v-window-item>
        <v-window-item value="experience">
          <h2>Experiências</h2>
          <div class="resumeCard pl-4">
            <h3>
              <v-icon>mdi-briefcase</v-icon> nPITI - Núcleo de Pesquisa e
              Inovação em Tecnologia da Informação - IMD/UFRN
            </h3>
            <p>2019 - 2021</p>
            <p class="mt-4">
              Desenvolvimento de uma platarforma para jogos educacionais.
            </p>
            <p class="mt-1 text-body-2">
              Ferramentas utilizadas: HTML, JavaScript e CSS, com o auxílio de
              bibliotecas como Bootstrap e JQuery
            </p>
          </div>
          <div class="resumeCard pl-4">
            <h3>
              <v-icon>mdi-briefcase</v-icon> Superintendencia de Tecnologia da
              Informação da UFRN - STI/UFRN
            </h3>
            <p>2020 - 2022</p>
            <p class="mt-4">
              Bolsista de desenvolvimento front-end, atuando no desenvolvimento
              de um Design System que serve de modelo para toda a Universidade
              Federal do Rio Grande do Norte, implementando, atualizando e
              testando componetes, páginas e portais.
            </p>
            <p class="mt-1 text-body-2">
              Ferramentas utilizadas: HTML, Pug.Js, JavaScript, JQuery, SCSS,
              Bootstrap, Cypress.JS, Jest.JS
            </p>
          </div>
        </v-window-item>
        <v-window-item value="skills">
          <h2>Habilidades</h2>
          <v-row>
            <v-col v-for="(item, index) in items" :key="index" cols="auto" class="skill-icons">
              <v-icon :icon="'mdi-'+item.icon"></v-icon>
            </v-col>
          </v-row>
        </v-window-item>
      </v-window>
    </v-container>
    <hr class="d-none d-md-flex" />
  </v-container>
</template>

<script>
export default {

  name: "ResumeCv",

  created() {
    window.addEventListener("resize", this.tabMenu);
  },

  data: () => ({
    tab: "",
    windowWidth:(window.outerWidth>960)?'vertical':'horizontal',
    items: [
        { icon: "language-javascript" },
        { icon: "language-html5" },
        { icon: "language-css3" },
        { icon: "vuejs" },
        { icon: "vuetify" },
        { icon: "bootstrap" },
        { icon: "nodejs" },
        { icon: "git" },
        { icon: "linux" },
        { icon: "language-python" },
        { icon: "raspberry-pi" },
        { icon: "language-cpp" },
      ],
  }),

  methods:{
    tabMenu() {
      this.windowWidth = (window.outerWidth>960)?'vertical':'horizontal';
    }
  }
  
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

.v-window-item{
  max-width: 800px;
}

.resumeCv {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  margin-top: 200px;
  height: auto;

  @media (max-width: 960px) {
    flex-direction: column;
  }

  .resumeCard {
    margin-top: 40px;
    padding: 20px;
    background-color: transparent;
    border: 4px solid #38d7f06c;
    border-radius: 10px;
    text-align: justify;
    max-width: 700px;
    transition: border-color 0.2s;

    &:hover {
      border-color: $sky-blue-crayola;
    }

    .v-icon {
      margin-right: 10px;
      margin-bottom: 10px;
      color: $sky-blue-crayola;
    }
  }
}

.v-row{
  align-content: center;
  justify-content: center;
  align-items: center;

  .skill-icons{
    font-size: 80px;

    :hover{
      color: $sky-blue-crayola;
      transition: all 1s !important;
    }
  }

}
</style>
