<template>
    <div class="page-container black-background">
      <div class="header">
        <ion-button href="/">Voltar</ion-button>
      </div>
  
      <div class="content ion-padding ion-text-center">
        <h1>Create your profile</h1>
        <p>Or log in to an existing account</p>
        
        <div class="form-group ion-margin-top">
          <ion-label>Email</ion-label>
          <ion-input v-model="email" type="email"></ion-input>
        </div>
        
        <div class="form-group ion-margin-top">
          <ion-label>Password</ion-label>
          <ion-input v-model="password" type="password"></ion-input>
        </div>
        
        <ion-button class="custom-button ion-margin-top" @click="continueClicked">Continue</ion-button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        email: '',
        password: ''
      };
    },
    methods: {
      continueClicked() {
        // Implemente a lógica de cadastro aqui
        // Por exemplo, enviar dados para um servidor ou navegar para a próxima tela
      }
    }
  };
  </script>
  
  <style scoped>

.page-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
  justify-content: space-between;
}

.black-background {
  background-color: #000000;
  color: white;
}

.header {
  padding: 16px;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center; /* centraliza na horizontal */
  justify-content: center; /* centraliza na vertical */
  flex: 1; /* faz com que este bloco ocupe todo o espaço disponível para o conteúdo centralizado */
}

.form-group {
  display: flex;
  flex-direction: column;
}
  .custom-button {
    --background: #7D00A9;
    --color: white;
    --border-radius: 5px;
    --ion-font-weight: bold;
    font-size: 21px;
    --padding: 15px 0;
    width: 100%;
  }

  
  </style>
  