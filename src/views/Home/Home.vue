<template>
  <v-main>
    <v-container fill-height class="pt-16">
    <Linkdin v-show="mobile" class="mr-5"  />
    <Github  v-show="mobile"/>
    <v-row justify="center" >
        <v-col cols="12" sm="4" :class="mobile ? pa-10 : pa-16">
            <p class="text-h6">olá, meu nome é:</p>
            <hr v-show="!mobile" />
            <p class="text-h2 font-weight-bold">Otávio</p>
              <v-img
                v-if="mobile" 
                src="https://i.pinimg.com/originals/f5/d9/8b/f5d98b3e305d45533bd32d558c70c5d9.jpg"
                alt="John"
                width="350"
              ></v-img>
              <br />
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia placeat debitis sit vero, laboriosam porro voluptatum id facilis quis? Eaque perferendis autem, consequatur iste quibusdam laudantium pariatur similique minima fuga quasi qui, nostrum a?</p>
              <v-btn width="500" class="mt-10 shw" color="primary" size="x-large">About me</v-btn>
          </v-col>
        <v-avatar class="ml-16" v-show="!mobile" size="280">
          <v-img
            src="https://i.pinimg.com/originals/f5/d9/8b/f5d98b3e305d45533bd32d558c70c5d9.jpg"
            alt="John"
          ></v-img>
        </v-avatar>
      </v-row>
</v-container>

  <about :widthDevice="mobile" />
  <storyLine />
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
    contact
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