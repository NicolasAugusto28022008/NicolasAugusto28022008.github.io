<script>
    const reyna = {
      name: "Reyna",
      description: "Reyna é uma duelista letal, especializada em eliminar inimigos com precisão e se curar após cada abate.",
      image: "/reyna.jpg",
      abilities: [
        "Leer: Crie uma esfera que distorce a visão dos inimigos, tornando-os mais vulneráveis.",
        "Dismisso: Após matar um inimigo, Releza uma habilidade que a torna invulnerável e se reposiciona.",
        "Consumo: Consome a alma de um inimigo derrotado para se curar.",
        "Ultimate: Transforme-se em um predador imbatível por um tempo, com habilidades aprimoradas."
      ]
    };
  </script>
  
  <div class="reyna-page">
    <h1 class="reyna-title">{reyna.name}</h1>
    <div class="reyna-container">
      <img class="reyna-image" src={reyna.image} alt={reyna.name} />
      <div class="reyna-info">
        <p class="reyna-description">{reyna.description}</p>
        <h2>Habilidades:</h2>
        <ul class="reyna-abilities">
          {#each reyna.abilities as ability}
            <li>{ability}</li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
  
  <style>
    .reyna-page {
      background-image: url("/background-agentes.jpg");
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
      background-attachment: fixed; /* Isso faz o fundo ser fixo */
      height: 100vh;
      color: white;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 20px;
      text-align: center;
    }
  
    .reyna-title {
      font-size: 4em;
      font-weight: bold;
      margin-bottom: 20px;
    }
  
    .reyna-container {
      display: flex;
      justify-content: center;
      gap: 40px;
      align-items: center;
      background-color: rgba(0, 0, 0, 0.6); /* Fundo escuro e semi-transparente */
      border-radius: 15px;
      padding: 20px;
    }
  
    .reyna-image {
      width: 300px;
      height: auto;
      border-radius: 15px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
    }
  
    .reyna-info {
      max-width: 500px;
    }
  
    .reyna-description {
      font-size: 1.2em;
      margin-bottom: 20px;
    }
  
    .reyna-abilities {
      list-style-type: none;
      padding: 0;
      font-size: 1.1em;
    }
  
    .reyna-abilities li {
      margin-bottom: 10px;
    }
  </style>
  