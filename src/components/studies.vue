<template>
<div :id="title"></div>
<v-container fill-height class="pt-16 case-studies">
  <p class="title" style="text-align: center;">{{ title }}</p>
  <v-slide-group
      v-model="model"
      class="pa-4"
      selected-class="bg-primary"
      show-arrows
    >
      <v-slide-group-item
        v-for="item in caseStudies"
        :key="item"
        v-slot="{ isSelected, toggle, selectedClass }"
      >
        <v-card
          :class="['ma-4', selectedClass]"
          :color="item.itens[0].color"
          height="200"
          width="100"
          variant="outlined"
          @click="toggle"
        >
        <v-card-title class="text-h5">
          <i 
            :class="item.icon"
            ></i>
        </v-card-title>
        <v-card-subtitle>{{ item.name }}</v-card-subtitle>

          <div class="d-flex fill-height align-center justify-center">
            <v-scale-transition>
              <v-icon
                v-if="isSelected"
                color="white"
                size="20"
                icon="mdi-close-circle-outline"
              ></v-icon>
            </v-scale-transition>
          </div>
        </v-card>
      </v-slide-group-item>
    </v-slide-group>

    <v-expand-transition>
      <v-sheet
        v-if="model != null"
        height="300"
      >
        <div class="d-flex fill-height align-center justify-center">
          <v-col cols="12">
          <v-card
            :color="caseStudies[model].itens[0].color"
            theme="dark" 
          >
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title class="text-h6">{{ caseStudies[model].itens[page].name }}</v-card-title>

                <v-card-subtitle>{{ caseStudies[model].itens[page].disMin }}</v-card-subtitle>

                <v-card-actions>
                  <v-btn
                    v-if="caseStudies[model].itens[page].demo != '/'"
                    class="ms-2"
                    variant="outlined"
                    :href="caseStudies[model].itens[page].demo"
                    size="small"
                  >
                    DEMO
                  </v-btn>
                </v-card-actions>
              </div>

              <v-avatar
                class="ma-3"
                size="125"
                rounded="0"
              >
                <v-img style="border-radius: 10px;" :src="caseStudies[model].itens[page].image"></v-img>
              </v-avatar>
            </div>
    <v-col cols="auto">
      <v-dialog
        transition="dialog-bottom-transition"
      >
        <template v-slot:activator="{ props }">
          <v-btn
            variant="outlined"
            size="small"
            width="100%"
            v-bind="props"
          >abrir detalhes</v-btn>
        </template>
        <template v-slot:default="{ isActive }">
          <v-card>
            <v-toolbar
              color="primary"
              title="Detalhes"
            ></v-toolbar>
            <v-card-text>
              <div>{{ caseStudies[model].itens[page].script }}</div>
            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                variant="outlined"
                size="small"
                @click="isActive.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>
          </v-card>
          <div class="text-center">
            <v-pagination
              v-model="page"
              :length="caseStudies[model].itens.length-1"
              rounded="circle"
            ></v-pagination>
          </div>
        </v-col>
        </div>
      </v-sheet>
    </v-expand-transition>
</v-container>
<br>
<br>
<br>
</template>
<script>
import studiesJson from '../data/studies.json'
import recentworks from '../data/recentworks.json'

export default {
    name: "studies",
    props: ["wr"],
    data() {
        return {
            model: null,
            page: 1,
            caseStudies: this.wr ? recentworks : studiesJson,
            title: this.wr ? 'Profisional Works' : 'Case Studies'
        }
    },
}
</script>
<style>
.title {
  font-family: 'Mohave';
  font-size: 42px;
}
</style>