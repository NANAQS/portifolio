<template>
  <h1 id="servico" class="mb-16 title" style="text-align: center;">Serviços</h1> 
  <div style="display: flex; justify-content: center; align-items: center;" class="mb-16">
    <v-chip variant="outlined" @click="click(0)" class="mr-5">Web</v-chip>
    <v-chip variant="outlined" @click="click(1)" class="mr-5">Mobile</v-chip>
  </div>
    <div :style="!mobile ? 'display: flex;justify-content: space-between;' : ''">
      <v-card
      class="mx-auto mb-4"
      width="344"
      v-for="item, i in data"
    >
      <v-img
        :src="'/public/semente'+i+'.png'"
        height="300px"
        cover
      ></v-img>

      <v-card-title>
        {{ item.name }}      
      </v-card-title>

      <v-card-subtitle style="word-wrap: break-word;white-space: -moz-pre-wrap;white-space: pre-wrap;">
        <div style="display: flex;justify-content: space-between;">
          <p>{{ item.description }}</p>
        </div>
      </v-card-subtitle>

      <v-card-actions style="display: flex; justify-content: center; align-items: center;">
        <v-btn
          style="position: absolute; bottom: 0"
          color="orange-lighten-2"
          variant="text"
          href="#contato"
        >
          Saber Mais
        </v-btn>

        <v-spacer></v-spacer>
      </v-card-actions>
    </v-card>
    </div>
</template>
<script>
import services from '../data/services.json'

  export default {
    props: ["widthDevice"],
    data() {
        return {
            data: services[0],
            mobile: this.widthDevice,
        }
    },
    methods: {
      async click(index) {
        this.data = services[index]
        await this.$nextTick();
      }
    }
  }
</script>

<style scoped>
.title {
  font-family: 'Mohave';
  font-size: 42px;
}
</style>