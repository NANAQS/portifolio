<template>
  <v-app>
    <v-app-bar v-if="!ok">
      <v-spacer></v-spacer>
      <a href="#home"><p class='defaultFont'>Home</p></a>
      <p class='defaultFont'>Case studies</p>
      <p class='defaultFont'>Testimonials</p>
      <p class='defaultFont'>Recent work</p>
      <p class='defaultFont'>About me</p>
      <v-spacer></v-spacer>
      <v-btn @click="toggleTheme" :prepend-icon="theme === 'dark' ? 'mdi-weather-night' : 'mdi-weather-sunny'"></v-btn>
      <Linkdin />
      <Github />
    </v-app-bar>
    <div id="home"></div>

    <router-view :widthDevice="ok"/>

    <v-navigation-drawer
        v-model="drop"
        location="bottom"
        temporary
      >
      <v-container>
          <v-btn class="mb-4 bg-surface-variant">Testimonials</v-btn>
          <v-spacer></v-spacer>
          <v-btn class="mb-4 bg-surface-variant">Recent work</v-btn>
          <v-spacer></v-spacer>
          <v-btn class="mb-4 bg-surface-variant"  @click="toggleTheme" :prepend-icon="theme === 'dark' ? 'mdi-weather-night' : 'mdi-weather-sunny'">Theme</v-btn>
          <v-spacer></v-spacer>
    </v-container>
      </v-navigation-drawer>

    <v-bottom-navigation v-if="ok">
      <v-btn href="#home" value="Home">
        <v-icon>mdi-home-circle</v-icon>
        Home
      </v-btn>

      <v-btn value="case_studies">
        <v-icon>mdi-microsoft-visual-studio-code</v-icon>

        Case studies
      </v-btn>

      <v-btn value="about">
        <v-icon>mdi-heart</v-icon>

        About me
      </v-btn>
      
      <v-btn value="more" @click="drop = !drop">
        <v-icon>mdi-more</v-icon>

        more options
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
import { ref } from 'vue'
import { useTheme } from 'vuetify'
import Linkdin from './components/LinkedinIcon.vue'
import Github from './components/Github.vue'
export default {
  name: "Home",
  setup() {
    const theme = useTheme()

    return {
      theme,
      toggleTheme: () => theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
    }
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
      theme: ref('dark')
    }
  },
  mounted() {
    if (this.windowWidth > 1000) {
      this.ok = false
    }
  },
  methods: {
    onClick() {
      console.log("CLICK");
      this.theme = this.theme === 'light' ? 'dark' : 'light'
    },
  }
}
</script>

<style>
a {
  text-decoration: none;
  color: unset;
}

.defaultFont {

  padding-left: 100px;
  font-family: 'IBM Plex Mono';

}
html {
  scroll-behavior: smooth;
}
</style>