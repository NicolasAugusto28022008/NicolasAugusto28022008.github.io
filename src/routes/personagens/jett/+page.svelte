<script>
    const jett = {
      name: "Jett",
      description: "Jett é uma duelist radiante que usa a agilidade e o vento para se mover rapidamente pelo campo de batalha, surpreendendo seus inimigos.",
      image: "/jett.jpg",
      abilities: [
        "Cloudburst: Crie uma nuvem de fumaça que obscurece a visão, podendo ser usada para bloquear a linha de visão dos inimigos.",
        "Updraft: Aumente sua altura, permitindo saltos maiores.",
        "Tailwind: Use um impulso para se mover rapidamente em qualquer direção.",
        "Ultimate: Lançar um tornado devastador que empurra e causa dano aos inimigos em sua trajetória."
      ]
    };
  </script>
  
  <div class="jett-page">
    <h1 class="jett-title">{jett.name}</h1>
    <div class="jett-container">
      <img class="jett-image" src={jett.image} alt={jett.name} />
      <div class="jett-info">
        <p class="jett-description">{jett.description}</p>
        <h2>Habilidades:</h2>
        <ul class="jett-abilities">
          {#each jett.abilities as ability}
            <li>{ability}</li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
  
  <style>
    .jett-page {
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
  
    .jett-title {
      font-size: 4em;
      font-weight: bold;
      margin-bottom: 20px;
    }
  
    .jett-container {
      display: flex;
      justify-content: center;
      gap: 40px;
      align-items: center;
      background-color: rgba(0, 0, 0, 0.6); /* Fundo escuro e semi-transparente */
      border-radius: 15px;
      padding: 20px;
    }
  
    .jett-image {
      width: 300px;
      height: auto;
      border-radius: 15px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
    }
  
    .jett-info {
      max-width: 500px;
    }
  
    .jett-description {
      font-size: 1.2em;
      margin-bottom: 20px;
    }
  
    .jett-abilities {
      list-style-type: none;
      padding: 0;
      font-size: 1.1em;
    }
  
    .jett-abilities li {
      margin-bottom: 10px;
    }
  </style>
  