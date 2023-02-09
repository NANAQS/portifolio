<template>
    <v-footer
      class="text-center d-flex flex-column"
    >
      <div>
        <v-btn
          v-for="icon in icons"
          :key="icon[0]"
          class="mx-4"
          :href="icon[1]"
          :icon="icon[0]"
          variant="text"
        ></v-btn>
      </div>
  
      <div class="pt-0">
        Agradeço por ver meu portifolio e espero sua mensagem :)
      </div>
  
      <v-divider></v-divider>
  
      <div>
        <strong>© Otávio Felema Rocha </strong> - {{ new Date().getFullYear() }} 
      </div>
    </v-footer>
  </template>
  
<script>
export default {
    data: () => ({
      icons: [
        ['mdi-linkedin', 'https://www.linkedin.com/in/otaviofelemarocha/'],
        ['mdi-github', 'https://github.com/NANAQS'],
      ],
    })
}
</script>
<style>
    
</style>