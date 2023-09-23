<template>
  <div class="container">
    <div class="divform">
      <img src="../assets/4907.png" alt="Logo do Banco" class="logo">
      <p class="textoinput" :class="{ 'valor-verde': valor >= 0, 'valor-vermelho': valor < 0 }">Olá, {{ dadosCadastro.nome }}, você tem: {{ this.valor }} na conta!</p>
      <div class="input-container">
        <span class="prefixo">R$</span>
        <input type="text" class="valor" min="100" placeholder="Digite o valor" v-model="valor2" @input="filtrarNumeros">
      </div>
      <div class="botoes">
        <button v-on:click="realizarDeposito" class="enviar">Depositar</button>
        <button v-on:click="realizarSaque" class="enviar">Sacar</button>
      </div>
    </div>
  </div>
  <estiloCliente/>
</template>

<script>
import estiloCliente from '../styles/estiloCliente.vue'

export default {
  name: 'TelaCliente',
  components:{
    estiloCliente,
  },
  props: {
    dadosDeposito: Object,
    dadosCadastro: Object
  },
  data() {
    return {
      valor2:'',
      valor: '',
    }
  },
  created(){
    this.valor = this.dadosDeposito.valor;
    
  },
  methods: {
    realizarDeposito() {
      this.valor = parseInt(this.valor) + parseInt(this.valor2);
      this.valor2 = '';
    },
    realizarSaque() {
      this.valor = parseInt(this.valor) - parseInt(this.valor2);
      this.valor2 = '';
    },
    filtrarNumeros() {
      this.valor2 = this.valor2.replace(/\D/g, ''); 
    }
  }
}
</script>

<style >

</style>
