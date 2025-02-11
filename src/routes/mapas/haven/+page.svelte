<script>
    let map = {
        name: "Haven",
        image: "/haven.jpg",
        description: "Haven é um mapa caracterizado por três pontos de bombsite e um layout assimétrico que exige um alto nível de comunicação e coordenação entre os jogadores. A diversidade de pontos de controle e a complexidade do mapa tornam-no um desafio para todas as equipes.",
        features: [
            "🗺 Localização: Região costeira",
            "🔹 Três pontos de bombsite (A, B e C)",
            "🔹 Layout assimétrico que desafia o controle de mapa",
            "🔹 Vários ângulos e alturas para combate",
            "🔹 Controle de middle e a rotação rápida são essenciais"
        ]
    };
</script>

<div class="map-page">
    <h1 class="map-title">{map.name}</h1>
    <div class="map-container">
        <img class="map-image" src={map.image} alt={map.name} />
        <div class="map-info">
            <p class="map-description">{map.description}</p>
            <h2>Características:</h2>
            <ul class="map-features">
                {#each map.features as feature}
                    <li>{feature}</li>
                {/each}
            </ul>
        </div>
    </div>
</div>

<style>
    .map-page {
        background-color: #0f1923;
        color: white;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px;
        font-family: Arial, sans-serif;
    }

    .map-title {
        font-size: 3em;
        font-weight: bold;
        margin-bottom: 20px;
        text-transform: uppercase;
    }

    .map-container {
        display: flex;
        flex-direction: row;
        align-items: center;
        background-color: rgba(0, 0, 0, 0.6);
        border-radius: 15px;
        padding: 20px;
        gap: 40px;
        max-width: 900px;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
    }

    .map-image {
        width: 400px;
        height: auto;
        border-radius: 15px;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
    }

    .map-info {
        max-width: 500px;
    }

    .map-description {
        font-size: 1.2em;
        margin-bottom: 20px;
    }

    .map-features {
        list-style-type: none;
        padding: 0;
        font-size: 1.1em;
    }

    .map-features li {
        margin-bottom: 10px;
    }
</style>
