<template>
    <div class="welcome-page">
      <div class="app-name">
        <h1>ANONY</h1>
        <p>{{ fixedText }} <span class="dynamic-text">{{ changingWords[selectedWordIndex] }}</span></p>
      </div>
      <div class="icon">
        <!-- Coloque seu ícone aqui -->
        <!-- Por exemplo: <img src="caminho-para-seu-icone" alt="Ícone" /> -->
      </div>
      <div class="continue-button">
        <ion-button class="custom-button">Continue</ion-button>
        <p class="terms-text">You agree to our Terms of Use and Privacy Policy by continuing</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
        return {
        fixedText: 'Share your',
        changingWords: ['videos', 'moments', 'photos', "NFT's"],
        selectedWordIndex: 0
        };
    },
    methods: {
        // Função para alternar as palavras
        changeWord() {
        this.selectedWordIndex = (this.selectedWordIndex + 1) % this.changingWords.length;
        }
    },
    created() {
      const prefersDarkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
  
      // Adicione a classe "dark" ao corpo do documento se o esquema de cores preferido for escuro
      if (prefersDarkMode) {
        document.body.classList.add('dark');
        
      }
      setInterval(this.changeWord, 2000);
    },
  };
  </script>
  
  <style scoped>
  .welcome-page {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    text-align: center;
    background-color: #000000;
    color: white;
  }
  
  .app-name {
    margin-bottom: 20px;
    font-size: 4vh;
  }

  .app-name h1 {
    margin-bottom: 20px;
    font-size: 6vh;
  }
  
  .icon {
    /* Estilos para o ícone */
  }
  
  .continue-button {
    width: 80%;
    position: absolute;
    bottom: 80px;
    text-align: center;
  }
  
  .continue-button button {
    width: 90%; /* Ajuste a largura conforme necessário */
    margin: 0 auto;
    font-size: 20px; /* Tamanho da fonte maior */
    font-weight: bold; /* Fonte chamativa */
    color: white; /* Cor da fonte branca */
    background-color: #7D00A9; /* Cor de fundo roxo */
    border: none;
    border-radius: 5px; /* Borda arredondada */
    padding: 15px 0; /* Espaçamento interno do botão */
    }

    .custom-button {
    --background: #7D00A9; /* Cor de fundo roxa para o botão */
    --color: white; /* Cor do texto branco para o botão */
    --border-radius: 5px; /* Borda arredondada */
    font-size: 21px; /* Tamanho da fonte maior para o botão */
    --font-weight: bold; /* Fonte chamativa para o botão */
    --padding: 15px 0; /* Espaçamento interno do botão */
    width: 90%;
    }

  .terms-text {
  font-size: 14px;
  color: #888888; /* Cor de cinza mais escuro */
  margin-top: 10px;
}

.dynamic-text {
  color: #0eb108; /* Cor verde para o texto dinâmico */
  transition: opacity 0.5s ease; /* Adiciona uma transição de fade out para a propriedade opacity */
}


  </style>
  