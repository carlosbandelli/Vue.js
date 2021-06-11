<template>
  <div id="app">    
    <input type="text" v-model="clienteCarlos.nome">    
    <input type="text" v-model="clienteCarlos.email">    
    <div v-for="(cliente,index) in clientes" :key="cliente.id">
        <h4>Edição: </h4>        
        <input type="text" v-model="cliente.nome">    
        <input type="text" v-model="cliente.email">
        <h4>{{ index + 1 }}</h4> 
        <Cliente :cliente="cliente"/>
        <hr>    
        
    </div>
  </div>
</template>

<script>

import Cliente from './components/Cliente'


export default {
  name: 'App',
  data(){
    return{
      nomeDoCarlos:"Carlos Ap. B. Vieira",
      clienteCarlos: {
        nome: "Carlos Bandelli",
        email: "Carlos@bandelli.com",
        idade: 99
      },
      clientes: [
        {
          id:2,
          nome: "Victor Lima",
          email: "victor@lima.com",
          idade: 99
        },
        {
          id:22,
          nome: "Michael Scott",
          email: "michael@lima.com",
          idade: 45
        },
        {
          id: 45,
          nomme: "Ednaldo Pereira",
          email: "edanaldopereira.chance@yahoo.com",
          idade: 86
        },
      ]
    }
  },
  components:{
    Cliente,    
  }
 
}
</script>

<style>

</style>
