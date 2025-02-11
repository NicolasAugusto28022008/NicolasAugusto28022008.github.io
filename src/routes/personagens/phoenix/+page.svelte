<script>
    const phoenix = {
      name: "Phoenix",
      description: "Phoenix é um duelist radiante que se destaca em combate. Ele usa suas habilidades para se curar, controlar o campo de batalha e causar danos significativos aos inimigos.",
      image: "/phoenix.jpg",
      abilities: [
        "Blaze: Crie uma parede de fogo que bloqueia a visão e cura Phoenix se ele estiver dentro dela.",
        "Curveball: Lance uma granada de flash ao redor de cantos, cegando temporariamente os inimigos.",
        "Hot Hands: Cure-se ou cause dano aos inimigos em um pequeno raio.",
        "Ultimate: Ressuscite a si mesmo após ser eliminado, se estiver dentro do alcance de seus companheiros de time."
      ]
    };
  </script>
  
  <div class="phoenix-page">
    <h1 class="phoenix-title">{phoenix.name}</h1>
    <div class="phoenix-container">
      <img class="phoenix-image" src={phoenix.image} alt={phoenix.name} />
      <div class="phoenix-info">
        <p class="phoenix-description">{phoenix.description}</p>
        <h2>Habilidades:</h2>
        <ul class="phoenix-abilities">
          {#each phoenix.abilities as ability}
            <li>{ability}</li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
  
  <style>
    .phoenix-page {
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
  
    .phoenix-title {
      font-size: 4em;
      font-weight: bold;
      margin-bottom: 20px;
    }
  
    .phoenix-container {
      display: flex;
      justify-content: center;
      gap: 40px;
      align-items: center;
      background-color: rgba(0, 0, 0, 0.6); /* Fundo escuro e semi-transparente */
      border-radius: 15px;
      padding: 20px;
    }
  
    .phoenix-image {
      width: 300px;
      height: auto;
      border-radius: 15px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
    }
  
    .phoenix-info {
      max-width: 500px;
    }
  
    .phoenix-description {
      font-size: 1.2em;
      margin-bottom: 20px;
    }
  
    .phoenix-abilities {
      list-style-type: none;
      padding: 0;
      font-size: 1.1em;
    }
  
    .phoenix-abilities li {
      margin-bottom: 10px;
    }
  </style>
  