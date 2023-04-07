<template>
  <h1 id="servico" class="mb-16 title" style="text-align: center;">Skills</h1> 
  <div :class="mobile ? 'b' : 'a'">
    <v-container>
    <v-row justify="space-around">
      <v-card width="300" height="400">
        <v-card-text>
          <div class="font-weight-bold ms-1 mb-2">
            Front-End
          </div>
            <div class="center">
                <div class="parent">
                    <i class="devicon-html5-plain-wordmark"></i>
                    <i class="devicon-css3-plain-wordmark"></i>
                    <i class="devicon-javascript-plain"></i>    
                    <i class="devicon-tailwindcss-original-wordmark"></i>
                    <i class="devicon-bootstrap-plain-wordmark"></i>
                    <i class="devicon-wordpress-plain-wordmark"></i>                    
                    <i class="devicon-vuejs-plain-wordmark"></i>
                    <i class="devicon-vuetify-plain"></i>
                    <i class="devicon-php-plain"></i>
                </div>
            </div>
        </v-card-text>
      </v-card>
    </v-row>
  </v-container>
  <v-container>
    <v-row justify="space-around">
      <v-card width="300" height="400">
        <v-card-text>
          <div class="font-weight-bold ms-1 mb-2">
            Back-End
          </div>
          <div class="center">
                <div class="parent">
                    <i class="devicon-nextjs-plain-wordmark"></i>
                    <i class="devicon-react-original-wordmark"></i>
                    <i class="devicon-nodejs-plain-wordmark"></i>
                    <i class="devicon-typescript-plain"></i>
                    <i class="devicon-dart-plain-wordmark"></i>
                    <i class="devicon-flutter-plain"></i>
                </div>
            </div>
        </v-card-text>
      </v-card>
    </v-row>
  </v-container>
  <v-container>
    <v-row justify="space-around">
      <v-card width="300" height="400">
        <v-card-text>
          <div class="font-weight-bold ms-1 mb-2">
            Databases & ORM's
          </div>
          <div class="center">
                <div class="parent">
                    <i class="devicon-mysql-plain-wordmark"></i>
                    <i class="devicon-postgresql-plain-wordmark"></i>
                    <i class="devicon-sqlite-plain-wordmark"></i>
                    <i class="devicon-graphql-plain-wordmark"></i>
                    <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" id="IconChangeColor" height="60" width="60"><title>Prisma</title><path d="M21.8068 18.2848L13.5528.7565c-.207-.4382-.639-.7273-1.1286-.7541-.5023-.0293-.9523.213-1.2062.6253L2.266 15.1271c-.2773.4518-.2718 1.0091.0158 1.4555l4.3759 6.7786c.2608.4046.7127.6388 1.1823.6388.1332 0 .267-.0188.3987-.0577l12.7019-3.7568c.3891-.1151.7072-.3904.8737-.7553s.1633-.7828-.0075-1.1454zm-1.8481.7519L9.1814 22.2242c-.3292.0975-.6448-.1873-.5756-.5194l3.8501-18.4386c.072-.3448.5486-.3996.699-.0803l7.1288 15.138c.1344.2856-.019.6224-.325.7128z" id="mainIconPathAttribute"></path></svg>

                </div>
            </div>
        </v-card-text>
      </v-card>
    </v-row>
  </v-container>
  </div>
</template>

<script>
export default {
    name: "skills",
    props: ["widthDevice"],
    data() {
        return {
            mobile: this.widthDevice,
        }
    }
}
</script>

<style scoped>
    i {
        font-size: 50px;
        margin: 10px;
    }
    .a {
        display: flex;
        flex-direction: row;
    }
    .parent {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, 1fr);
        grid-column-gap: 0px;
        grid-row-gap: 0px;
    }
    .center {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .title {
        font-family: 'Mohave';
        font-size: 42px;
    }
</style>