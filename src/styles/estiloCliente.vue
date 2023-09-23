<template>
    <div></div>
   </template>
   
   <script>
   export default {
     name: 'estiloCliente',
   }
   </script>
   
   <style>
   .container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.divform {
  max-width: 400px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  background-color: #f4f4f4;
  padding: 20px;
  border-radius: 10px;
}

.textoinput {
  font-family: 'Arial', sans-serif;
  font-size: 16px;
  color: #333;
}

.valor {
  width: calc(100% - 22px);
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.enviar {
  background-color: #ff5722;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
  font-family: 'Arial', sans-serif;
  font-size: 16px;
  color: #fff;
}

.logo {
  max-width: 100%;
  height: auto;
}

.botoes {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}

.enviar {
  margin: 0 5px;
}

.input-container {
  display: flex;
  align-items: center;
}

.prefixo {
  margin-right: 8px;
  font-size: 16px;
}

.valor {
  width: calc(100% - 28px); 
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
}

.botoes {
  display: flex;
  justify-content: space-around;
}

.valor-verde {
  color: green !important; 
}

.valor-vermelho {
  color: red !important; 
}

   </style>
   