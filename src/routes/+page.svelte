<script>
	const gameInfo = {
		description: "Valorant é um jogo de tiro competitivo 5v5 onde os jogadores controlam 'Agentes', cada um com habilidades únicas, enquanto competem para cumprir objetivos como plantar ou desarmar a bomba.",
		features: [
			"🎯 Jogo de tiro tático e estratégico",
			"🔹 Agentes com habilidades únicas",
			"🔹 Modos de jogo competitivos e casuais",
			"🔹 Mapas com design dinâmico e inovador",
			"🔹 Grande foco em trabalho em equipe e comunicação"
		],
		images: [
			{ name: 'background', image: 'background-agentes.jpg' },
			{ name: 'logo', image: 'logo.png' }
		]
	};
</script>

<div class="background">
	<div class="content">
		<img class="game-logo" src={gameInfo.images[1].image} alt={gameInfo.images[1].name} />
		<h1 class="game-title">{gameInfo.title}</h1>
		<p class="game-description">{gameInfo.description}</p>

		<h2>Recursos:</h2>
		<ul class="game-features">
			{#each gameInfo.features as feature}
				<li>{feature}</li>
			{/each}
		</ul>

		<a href="/mapas" class="start-button">Começar</a>
	</div>
</div>

<style>
	.background {
		background-image: url("{gameInfo.images[0].image}");
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center;
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.content {
		text-align: center;
		color: rgb(0, 0, 0);
		background-color: rgb(255, 83, 83);
		padding: 40px;
		border-radius: 15px;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
	}

	.game-logo {
		width: 150px;
		height: auto;
		margin-bottom: 20px;
	}

	.game-title {
		font-size: 3em;
		font-weight: bold;
		margin-bottom: 20px;
	}

	.game-description {
		font-size: 1.2em;
		margin-bottom: 20px;
	}

	.game-features {
		list-style-type: none;
		padding: 0;
		font-size: 1.1em;
		margin-bottom: 30px;
	}

	.game-features li {
		margin-bottom: 10px;
	}

	.start-button {
		display: inline-block;
		background-color: #d3d3d3;
		color: rgb(0, 0, 0);
		padding: 10px 30px;
		font-size: 1.2em;
		font-weight: bold;
		border-radius: 5px;
		text-decoration: none;
		transition: background-color 0.3s;
	}

	.start-button:hover {
		background-color: #ffffff;
	}
</style>
