<template>
    <div id="about"></div>
    <v-col cols="12" class="mt-16">
        <div class="d-flex flex-no-wrap justify-space-between">
            <div :class="mobile ? 'ma-10' : ''">
                <v-img
                    class="bg-white"
                    width="300"
                    :aspect-ratio="1"
                    src="https://images.unsplash.com/photo-1459257868276-5e65389e2722?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80https://cdn.vuetifyjs.com/images/parallax/material.jpg"
                    cover
                    style="border-radius: 10px;"
                ></v-img>
            </div>    
            <v-col cols="12" v-show="!mobile">
                <h3>Informacões Extras</h3>
                <p style="width: 80%;">Nasci em taboão da serra - SP<br >mas atualmente moro em Ponta Grossa - PR<br>minha rota de estudos vão todo dia 5h de estudo sobre linguagens a qual me agrado mais<br/> e por fim em 2023 quero estudar mais sobre Flutter porque gostei muito da sintaxe da linguagem</p>
            </v-col>
        </div>
        <v-col style="text-align: center;" cols="12" v-show="mobile">
            <h1>Informacões Extras</h1>
            <p>Nasci em taboão da serra - SP<br>mas atualmente moro em Ponta Grossa - PR<br>minha rota de estudos vão todo dia 5h de estudo sobre linguagens a qual me agrado mais<br/> e por fim em 2023 quero estudar mais sobre Flutter porque gostei muito da sintaxe da linguagem</p>
        </v-col>
    </v-col>  
    <hr color="grey" />  
</template>

<script>
export default {
    props: ["widthDevice"],
    data() {
        return {
            mobile: this.widthDevice,
        }
    },
}
</script>
<style>
#inner {  
  border: 5em solid ;
  width: 20em;
  background: #000;
}

#outer {
  width:100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>