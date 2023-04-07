<template>

  <v-main>
    <v-container fill-height class="pt-16">
    <Linkdin v-show="mobile" class="mr-5 mb-5"  />
    <Github  v-show="mobile" class="mb-5"/>
    <v-row justify="center" >
        <v-col cols="12" sm="4" :class="mobile ? pa-10 : pa-16">
            <p class="text-h6">Olá, meu nome é:</p>
            <hr v-show="!mobile" />
            <p class="title">Otávio</p>
              <v-img
                v-if="mobile" 
                src="../../assets/face.jpg"
                alt="John"
                width="350"
                style="border-radius: 10px;"
              ></v-img>
              <br />
              <p>Sou programador focado em Front-end mas também já mexi com Back-end<br/><br/>Tenho 19 anos(ja fora do alistamento) e sou apaixonado por tecnologia desde meus 12 anos</p>
              <v-btn href="#about" width="500" class="mt-10 shw" color="primary" size="x-large">About me</v-btn>
          </v-col>
        <v-avatar class="ml-16" v-show="!mobile" size="280">
          <v-img
            src="../../assets/face.jpg"
            alt="John"
          ></v-img>
        </v-avatar>
      </v-row>
</v-container>

  <about :widthDevice="mobile" />
  <storyLine />
  <skills :widthDevice="mobile" />
  <services :widthDevice="mobile" />
  <studies />
  <studies wr="false" />
  
  <contact />
  </v-main>
</template>

<script>
import Linkdin from '../../components/LinkedinIcon.vue'
import Github from '../../components/Github.vue'

import studies from '../../components/studies.vue'
import storyLine from '../../components/storyLine.vue'
import about from '../../components/about.vue'
import contact from '../../components/contact.vue'
import services from '../../components/services.vue'
import skills from '../../components/skills.vue'


import { useTheme } from 'vuetify'

export default {
  name: "Home",
  props: ["widthDevice"],
  data() {
    return {
      mobile: this.widthDevice,
      theme: useTheme()
    }
  },
  components: {
    studies,
    storyLine,
    about,
    Linkdin,
    Github,
    services,
    contact,
    skills
  }
}
</script>

<style scoped>
.shw {
  box-shadow: 0px 15px 20px #f7aff71f;
}
.fontDefault {
  font-family: 'IBM Plex Mono';
}
.title {
  font-family: 'Mohave';
  font-size: 42px;
}
</style>