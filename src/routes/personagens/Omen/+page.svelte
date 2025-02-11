<script>
    const omen = {
      name: "Omen",
      description: "Omen é um agente misterioso com habilidades focadas em manipular sombras para confundir seus inimigos e controlar o mapa.",
      image: "/omen.jpg",
      abilities: [
        "Shrouded Step: Teleporte para um local próximo, desaparecendo temporariamente.",
        "Paranoia: Envie uma sombra através de uma linha reta para cegar e desorientar inimigos.",
        "Dark Cover: Crie uma esfera de sombra que pode ser movida e usada para bloquear a visão.",
        "Ultimate: Envie uma sombra para qualquer lugar do mapa, desorientando os inimigos e criando caos."
      ]
    };
  </script>
  
  <div class="omen-page">
    <h1 class="omen-title">{omen.name}</h1>
    <div class="omen-container">
      <img class="omen-image" src={omen.image} alt={omen.name} />
      <div class="omen-info">
        <p class="omen-description">{omen.description}</p>
        <h2>Habilidades:</h2>
        <ul class="omen-abilities">
          {#each omen.abilities as ability}
            <li>{ability}</li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
  
  <style>
    .omen-page {
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
  
    .omen-title {
      font-size: 4em;
      font-weight: bold;
      margin-bottom: 20px;
    }
  
    .omen-container {
      display: flex;
      justify-content: center;
      gap: 40px;
      align-items: center;
      background-color: rgba(0, 0, 0, 0.6); /* Fundo escuro e semi-transparente */
      border-radius: 15px;
      padding: 20px;
    }
  
    .omen-image {
      width: 300px;
      height: auto;
      border-radius: 15px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
    }
  
    .omen-info {
      max-width: 500px;
    }
  
    .omen-description {
      font-size: 1.2em;
      margin-bottom: 20px;
    }
  
    .omen-abilities {
      list-style-type: none;
      padding: 0;
      font-size: 1.1em;
    }
  
    .omen-abilities li {
      margin-bottom: 10px;
    }
  </style>
  