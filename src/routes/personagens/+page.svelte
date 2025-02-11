<script>
	import { goto } from '$app/navigation';
	let agents = [
		{ name: 'Jett', image: '/jett.jpg' },
		{ name: 'Phoenix', image: '/phoenix.jpg' },
		{ name: 'Reyna', image: '/reyna.jpg' },
		{ name: 'Omen', image: '/omen.jpg' }
	];

	const handleClick = (name) => {
		goto(`/personagens/${name}`);
	};
</script>

<div class="background">
	<h1 class="title">AGENTES</h1>

	<div class="agents-container">
		{#each agents as agent}
			<div class="agent-card" on:click={() => handleClick(agent.name)}>
				<img class="agent-image" src={agent.image} alt={agent.name} />
				<div class="agent-name">{agent.name}</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.background {
		background-image: url("/background-agentes.jpg");
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center;
		background-attachment: fixed;
		height: 100vh;
		display: flex;
		flex-direction: column;
		padding: 20px;
	}

	.title {
		font-size: 500%;
		color: white;
		margin-bottom: 50px;
		text-align: center;
	}

	.agents-container {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 20px;
		padding: 20px;
	}

	.agent-card {
		background-color: #1a2633;
		border-radius: 10px;
		overflow: hidden;
		text-align: center;
		width: 12%;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
		transition: transform 0.2s;
		cursor: pointer;
	}

	.agent-card:hover {
		transform: scale(1.05);
	}

	.agent-image {
		width: 100%;
		height: auto;
	}

	.agent-name {
		padding: 10px;
		color: white;
		font-weight: bold;
	}
</style>
