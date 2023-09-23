<template>
  <div class="container">
    <div class="divform">
      <img src="../assets/4907.png" alt="Logo do Banco" class="logo">
      <p class="textoinput">Olá, {{ dadosCadastro.nome }} {{ dadosCadastro.sobrenome }}, Quanto você deseja depositar? </p>
      <h6>Valor mínimo R$100,00.</h6>
      <div class="input-container">
        <span class="prefixo">R$</span>
        <input type="text" class="valor" min="100" placeholder="Digite o valor" v-model="valor" @input="filtrarNumeros">
      </div>
      <button v-on:click="realizarDeposito" class="enviar" :disabled="!todosCamposPreenchidos || valor < 100" >Depositar</button>
    </div>
  </div>
  <estiloDeposito/>
</template>

<script>
import estiloDeposito from '../styles/estiloDeposito.vue'

export default {
  name: 'TelaDeposito',
  data() {
    return {
      valor: ''
    }
  },
  components: {
    estiloDeposito,
  },
  props:{
    dadosCadastro: Object
  },
  methods: {
    realizarDeposito() {
      this.$emit('depositar', {valor:this.valor });
    },
    filtrarNumeros() {
      this.valor = this.valor.replace(/\D/g, ''); 
    }
  },
  computed: {
    todosCamposPreenchidos() {
      return this.valor
    } 
  }
}
</script>
