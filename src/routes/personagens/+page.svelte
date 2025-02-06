<script>
	let agents = [
		{ name: 'jett', image: '/jett.jpg' },
		{ name: 'Phoenix', image: '/phoenix.jpg' },
		{ name: 'Sage', image: '/sage.jpg' },
		{ name: 'raze', image: '/raze.jpg' }
	];
</script>

<h1 class="title">AGENTES</h1>

<div class="agents-container">
	{#each agents as agent}
		<div class="agent-card">
			<img class="agent-image" src={agent.image} alt={agent.name} />
			<div class="agent-name">{agent.name}</div>
		</div>
	{/each}
</div>

<style>
	.title {
		font-size: 500%;
		color: white;
        margin-top: 100px;
        margin-left: 100px;
        margin-bottom: 50px;
	}

	.agents-container {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 20px;
		padding: 20px;
		background-color: #0f1923;
	}

	.agent-card {
		background-color: #1a2633;
		border-radius: 10px;
		overflow: hidden;
		text-align: center;
		width: 20%;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
		transition: transform 0.2s;
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
