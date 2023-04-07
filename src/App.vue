<template>
  <v-app>
    <v-app-bar style='backdrop-filter: blur(3px)' color="transparent" v-if="!ok">
      <v-spacer></v-spacer>
      <a href="#home"><p class="defaultFont">Home</p></a>
      <a href="#about"><p class="defaultFont">About Me</p></a>
      <a href="#Case Studies"><p class="defaultFont">Case studies</p></a>
      <a href="#servico"><p class="defaultFont">Serviço</p></a>
      <a href="#contato"><p class="defaultFont">Contato</p></a>
      <v-spacer></v-spacer>
      <v-btn @click="toggleTheme" prepend-icon="mdi-weather-sunny"> </v-btn>
      <Linkdin />
      <Github />
    </v-app-bar>
    <div id="home"></div>

    <router-view :widthDevice="ok" />

    <v-navigation-drawer v-model="drop" location="bottom">
      <v-container>
        <v-btn href="#servico" class="mb-4 bg-surface-variant w-100"
          >Serviço</v-btn
        >
        <v-btn href="#contato" class="mb-4 bg-surface-variant w-100"
          >Contato</v-btn
        >
        <v-spacer></v-spacer>
        <v-btn
          class="mb-4 bg-surface-variant w-100"
          @click="toggleTheme"
          prepend-icon="mdi-weather-sunny"
          >Theme</v-btn
        >
        <v-spacer></v-spacer>
      </v-container>
    </v-navigation-drawer>

    <v-bottom-navigation v-if="ok">
      <v-btn href="#home" value="Home">
        <v-icon>mdi-home-circle</v-icon>
        Home
      </v-btn>

      <v-btn href="#Case Studies" value="case_studies">
        <v-icon>mdi-microsoft-visual-studio-code</v-icon>
        Case studies
      </v-btn>

      <v-btn href="#about" value="about">
        <v-icon>mdi-heart</v-icon>
        About Me
      </v-btn>

      <v-btn value="more" @click="drop = !drop">
        <v-icon>mdi-more</v-icon>
        more options
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
import { ref } from "vue";
import { useTheme } from "vuetify";
import Linkdin from "./components/LinkedinIcon.vue";
import Github from "./components/Github.vue";

export default {
  name: "Home",
  setup() {
    const theme = useTheme();

    return {
      toggleTheme: () => {
        theme.global.name.value = theme.global.current.value.dark
          ? "light"
          : "dark";
        this.themeee = theme.global.name.value;
      },
    };
  },
  components: {
    Linkdin,
    Github,
  },
  data() {
    return {
      ok: true,
      drop: false,
      windowWidth: ref(window.innerWidth),
    };
  },
  mounted() {
    if (this.windowWidth > 1000) {
      this.ok = false;
    }
  },
};
</script>

<style>
a {
  text-decoration: none;
  color: unset;
}

.defaultFont {
  padding-left: 100px;
  font-family: "IBM Plex Mono";
}
html {
  scroll-behavior: smooth;
}
</style>
