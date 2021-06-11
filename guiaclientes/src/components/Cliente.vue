<template> 
    <div :class="{'cliente': !isPremium,'cliente-premium': isPremium}">
      <h4>Nome:{{cliente.nome}}</h4>
      <hr>
      <p>Email: {{cliente.email}}</p> 
      <p v-if="showIdade === true">Idade:{{cliente.idade}}</p>
      <p v-else>O usuario escondeu a idade!</p>
      <button @click="mudarCor($event)">Mudar cor!</button>
    </div>
</template>

<script>

export default {
   data(){
       return{
           isPremium: false
         
       }    
   },
   props: {
       
        cliente: Object,
        showIdade: Boolean
    },
    methods: {
        mudarCor: function($event){
            console.log($event),
            this.isPremium = !this.isPremium
            
        }

    }
}
</script>

<style scoped>
    .cliente{
        
        background-color: #CBC9CF;
        max-width: 600px;
        height: 180px;
        padding: 1%;
        margin-top: 2%;

    }

    .cliente-premium{
        background-color: black;
        color: yellow;
        max-width: 600px;
        height: 180px;
        padding: 1%;
        margin-top: 2%;

    }

    

</style>
