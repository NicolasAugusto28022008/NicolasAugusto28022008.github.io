<script>
    let weapon = {
        name: "Outlaw",
        image: "/outlawcard.jpg",
        description: "A Outlaw é um rifle de precisão semi-automático poderoso, capaz de eliminar inimigos com dois tiros rápidos no corpo. Ideal para jogadores agressivos que gostam de snipers.",
        attributes: [
            "🔹 Tipo: Rifle de Precisão",
            "🔹 Cadência de Tiro: Média",
            "🔹 Dano: Muito Alto",
            "🔹 Recuo: Baixo"
        ]
    };
</script>

<div class="weapon-page">
    <h1 class="weapon-title">{weapon.name}</h1>
    <div class="weapon-container">
        <img class="weapon-image" src={weapon.image} alt={weapon.name} />
        <div class="weapon-info">
            <p class="weapon-description">{weapon.description}</p>
            <h2>Atributos:</h2>
            <ul class="weapon-attributes">
                {#each weapon.attributes as attr}
                    <li>{attr}</li>
                {/each}
            </ul>
        </div>
    </div>
</div>

<style>
    .weapon-page {
        background-color: #0f1923;
        color: white;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px;
        font-family: Arial, sans-serif;
    }

    .weapon-title {
        font-size: 3em;
        font-weight: bold;
        margin-bottom: 20px;
        text-transform: uppercase;
    }

    .weapon-container {
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

    .weapon-image {
        width: 300px;
        height: auto;
        border-radius: 15px;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
    }

    .weapon-info {
        max-width: 500px;
    }

    .weapon-description {
        font-size: 1.2em;
        margin-bottom: 20px;
    }

    .weapon-attributes {
        list-style-type: none;
        padding: 0;
        font-size: 1.1em;
    }

    .weapon-attributes li {
        margin-bottom: 10px;
    }
</style>
