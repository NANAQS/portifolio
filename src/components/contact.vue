<template>
    <v-footer
      style="border-top-left-radius: 30px 30px; border-top-right-radius: 30px 30px;"
      class="text-center d-flex flex-column"
    >
    <div class="text-center d-flex flex-column">
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
    </div>
      <div>
        Agradeço por ver meu portifolio :)
      </div>

    <v-container id="contato">
          <v-text-field
            counter="20"
            label="Nome"
            v-model="named"
          ></v-text-field>
          <v-textarea
            counter
            label="Message"
            maxlength="120"
            v-model="msg"
            single-line
          ></v-textarea>
          <v-btn
            class="mb-10 w-100"
            variant="outlined"
            color="primary"
            @click="submit()"
          >
            submit
          </v-btn>
    </v-container>
  
      <v-divider></v-divider>
  
      <div>
        <strong>© Otávio Felema Rocha </strong> - {{ new Date().getFullYear() }} 
      </div>
    </v-footer>
  </template>
  
<script>
export default {
    data: () => ({
      msg: '',
      named: '',
      icons: [
        ['mdi-linkedin', 'https://www.linkedin.com/in/otaviofelemarocha/'],
        ['mdi-github', 'https://github.com/NANAQS'],
      ],
    }),
    methods: {
      submit() {
        let texto = encodeURI(this.msg)
        let baseurl = 
        "https://mail.google.com/mail/u/0/?view=cm&fs=1&tf=1&to=otaviotokyo5@gmail.com&subject="+
        "MISSED%20CALL%20EZTRADER&body=Ola%20meu+nome+é+"+this.named+",%0A%0A+"+texto
        window.location.href = baseurl
      }
    }
}
</script>
<style>
    
</style>