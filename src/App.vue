<template>
  <div>
    <div v-if="telaPrincipal === 'telaCadastro'">
      <telaCadastro @cadastrar="capturarDadosCadastro" />
    </div>
    <div v-else-if="telaPrincipal === 'telaDeposito'">
      <telaDeposito :dadosCadastro="dadosCapturados" @depositar="capturarDadosDeposito" />
    </div>
    <div v-else-if="telaPrincipal === 'telaCliente'">
      <TelaCliente :dadosDeposito="dadosCapDeposito" :dadosCadastro="dadosCapturados" />
    </div>
  </div>
</template>

<script>
import telaCadastro from './components/telaCadastro.vue'
import TelaCliente from './components/telaCliente.vue'
import telaDeposito from './components/telaDeposito.vue';

export default {
  name: 'App',
  data(){
    return {
      telaPrincipal: 'telaCadastro',
      dadosCapturados: null,
      dadosCapDeposito: null,
    }
  },
  methods:{
    trocarTelaDeposito(){
      this.telaPrincipal = 'telaDeposito';
    },
    trocarTelaCliente(){
      this.telaPrincipal = 'telaCliente';
    },
    capturarDadosCadastro(dados){
      this.dadosCapturados = dados;
      this.trocarTelaDeposito();
    },
    capturarDadosDeposito(dados){
      this.dadosCapDeposito = dados;
      this.trocarTelaCliente();
    }
  },
  components: {
    telaCadastro,
    telaDeposito,
    TelaCliente,
  }
}
</script>
