<template>
  <div></div>
</template>
 
<script>
export default {
  name: 'estiloCadastro',
}
</script>
 
<style>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.logo {
  max-width: 200px; 
  height: auto;
  margin-right: 20px; 
}

.divform {
  max-width: 400px;
  text-align: left;
}

.textoinput {
  font-family: 'Arial', sans-serif;
  font-size: 16px;
  color: #333;
}

.nome,
.sobrenome,
.email,
.cpf,
.senha,
.checkbox {
  width: calc(100% - 22px);
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.checkbox-container {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
  text-align: left;
}

.checkbox {
  margin: 0;
  margin-right: 10px;
  transform: scale(1.5);
  width: auto;
}

.checkbox-label {
  font-family: 'Arial', sans-serif;
  font-size: 16px;
  color: #333;
  margin: 0;
}

button {
  background-color: #ff5722;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
  color: #fff;
}

button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}
</style>
