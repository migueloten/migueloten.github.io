<template>
  <v-container class="header">
    <!-- logo no header -->
    <v-img class="my-auto" src="../assets/logo.png" />
    <!-- lista de menu no header -->
    <ol class="menu my-auto d-none d-md-flex">
      <li v-for="(item, index) in items" :key="index">
        <a :href="item.href"> {{ item.title }} </a>
      </li>
    </ol>
  </v-container>
  <!-- menu header - responsivo -->
  <v-navigation-drawer
    class="d-md-none"
    v-model="drawer"
    elevation="23"
    color="#001b2e"
    width="400"
    temporary
    position="right"
  >
    <v-list>
      <div class="listOptions">
        <div class="HeaderOption" v-for="(item, index) in items" :key="index">
          <v-icon>mdi-{{ item.icon }}</v-icon>
          <a :href="item.href"> {{ item.title }} </a>
        </div>
      </div>
    </v-list>
  </v-navigation-drawer>
  <v-main class="d-md-none" style="height: 50px">
    <div class="d-flex justify-center align-center h-100">
      <v-btn
        flat
        icon
        class="btn-responsivo"
        size="large"
        @click.stop="drawer = !drawer"
        @click="overlayStyle"
      >
        <v-icon>mdi-{{ drawer ? "close" : "menu" }}</v-icon>
      </v-btn>
    </div>
  </v-main>
</template>

<script>
export default {
  name: "HeaderPage",

  created() {
    window.addEventListener("scroll", this.onScroll);
  },

  data() {
    return {
      drawer: null,
      items: [
        { title: "Sobre mim", href: "#aboutMe", icon: "account" },
        { title: "Currículo", href: "#resumeCv", icon: "file-account" },
        { title: "Repositórios", href: "#repositories", icon: "github" },
        { title: "Contato", href: "#contact", icon: "email" },
      ],
    };
  },

  methods: {
    overlayStyle() {
      if (this.drawer) {
        setTimeout(() => {
          document.getElementsByClassName(
            "v-navigation-drawer__scrim"
          )[0].style.backgroundColor = "transparent";
          document.getElementsByClassName(
            "v-navigation-drawer__scrim"
          )[0].style.opacity = "unset";
          document.getElementsByClassName(
            "v-navigation-drawer__scrim"
          )[0].style.backdropFilter = "blur(10px)";
        }, 10);
      }
    },

    onScroll() {
      if (document.documentElement.scrollTop > 50) {
        document.getElementsByClassName("header")[0].style.height = "50px";
        document.getElementsByClassName("btn-responsivo")[0].style.top = "92%";
      } else {
        document.getElementsByClassName("header")[0].style.height = "120px";
        document.getElementsByClassName("btn-responsivo")[0].style.top = "30px";
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/variables.scss";

.header {
  background-color: transparentize($color: #000000, $amount: 0.93);
  backdrop-filter: blur(10px);
  font-weight: bold;
  display: flex;
  justify-content: space-between;
  position: fixed;
  top: 0;
  max-width: 100% !important;
  margin: 0;
  padding: 5px;
  min-height: 50px;
  height: 120px;
  transition: height 0.5s;
  z-index: 1;

  .v-img {
    width: 10%;
  }

  .menu {
    display: flex;
    justify-content: space-evenly;
    width: 80%;

    li {
      color: $sky-blue-crayola;
      font-size: 0.8rem;

      a {
        font-size: 0.8rem;
      }
    }
  }
}

.v-navigation-drawer {
  padding: 8px 35px;
  background-color: $oxford-blue !important;

  .v-list {
    background-color: transparent;
    height: 100%;

    .listOptions {
      height: 100%;
      text-align: center;
      padding-top: 40%;

      .HeaderOption {
        display: flex;
        align-items: center;
        align-content: center;
        flex-direction: column;
        justify-content: center;
        height: 20%;
        color: $sky-blue-crayola;

        .v-icon {
          font-size: 1.8rem;
        }
      }
    }
  }
}

.btn-responsivo.v-btn {
  position: fixed;
  right: 40px;
  top: 30px;
  transition: top 1s;
  z-index: 1010;
  background-color: transparent;
  color: $sky-blue-crayola;

  .v-icon {
    font-size: 40px;
  }
}
</style>
