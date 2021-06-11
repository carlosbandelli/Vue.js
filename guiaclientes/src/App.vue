<template>
  <div id="app">   
    <h3>Cadastro: </h3> 
    <small id="deuErro" v-show="deuErro">O nome é inválido, tente novamente!</small><br>
    <input type="text" placeholder="nome" v-model="nomeField"><br>    
    <input type="email" placeholder="email" v-model="emailField"><br>
    <input type="number" placeholder="idade" v-model="idadeField"><br>
    <button @click="cadastrarUsuario">Cadastrar</button>
    <hr>
    <div v-for="(cliente,index) in clientes" :key="cliente.id">       
        <h4>{{ index + 1 }}</h4> 
        <Cliente :cliente="cliente"/>        
    </div>
  </div>
</template>

<script>

import Cliente from './components/Cliente'


export default {
  name: 'App',
  data(){
    return{
      deuErro: false,
      nomeField:"",
      emailField:"",
      idadeField:0,
      
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
  },

  methods:{
    cadastrarUsuario: function(){

    if(this.nomeField == "" || this.nomeField == " " || this.nomeField.length < 3){
      this.deuErro = true
      console.log("Erro de validação")
    }else{
        this.clientes.push({
        nome: this.nomeField,
        email: this.emailField,
        idade: this.idadeField,
        id: Date.now()
        })
        this.nomeField = "";
        this.emailField = "";
        this.idadeField = 0;
        this.deuErro = false;
      }
    }
  }
 
}
</script>

<style>

#deuErro{
  color: red;
}

</style>
