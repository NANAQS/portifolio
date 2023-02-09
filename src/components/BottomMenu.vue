<template>
    <v-btn value="Home">
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

      <v-btn value="about">
        <v-icon>mdi-more</v-icon>

        more options
      </v-btn>
</template>
<script>
export default {
    name: "BottomMenu",
    methods: {
        onClick() {
            console.log("ok")
        }
    },
}
</script>