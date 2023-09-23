<template>
  <div class="container">
    <img src="../assets/4907.png" alt="Logo do Banco" class="logo">
    <div class="divform">
      <p class="textoinput">Digite seu nome</p>
      <input type="text" class="nome" placeholder="Digite seu nome" v-model="nome"> 
      <p class="textoinput">Digite seu sobrenome</p>
      <input type="text" class="sobrenome" placeholder="Digite seu sobrenome" v-model="sobrenome"> 
      <p class="textoinput">Email</p> 
      <input type="email" class="email" placeholder="Exemplo@exemplo.com.br" v-model="email">
      <p class="textoinput">CPF</p>
      <input type="text" class="cpf" placeholder="123.456.789-10" v-model="cpf">
      <p class="textoinput">Senha</p>
      <input type="password" class="senha" placeholder="Digite sua senha" v-model="senha">
      
      <div class="checkbox-container">
        <input type="checkbox" class="checkbox" :disabled="!todosCamposPreenchidos">
        <label class="checkbox-label">Li e concordo com os Termos de Uso e Políticas de Privacidade</label>
      </div>
      
      <button v-on:click="cadastrarUsuario" :disabled="!todosCamposPreenchidos">Enviar</button>
    </div>
  </div>
  <estiloCadastro/>
</template>

<script>
import estiloCadastro from '../styles/estiloCadastro.vue'

export default {
  name: 'telaCadastro',
  data(){
    return{
      nome:'',
      sobrenome:'',
      email:'',
      cpf:'',
      senha:'',
    }
  },
  methods:{
    cadastrarUsuario(){
      this.$emit('cadastrar',{
        nome:this.nome,
        sobrenome:this.sobrenome,
        email:this.email,
        cpf:this.cpf,
        senha:this.senha
      })
    },
  },
  computed: {
    todosCamposPreenchidos() {
      return this.nome && this.sobrenome && this.email && this.cpf && this.senha;
    } 
  },
  components:{
    estiloCadastro,
  }
}
</script>
