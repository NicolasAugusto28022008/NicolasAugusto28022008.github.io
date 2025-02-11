<script>
	import { goto } from '$app/navigation';

	let maps = [
		{ name: 'Haven', image: '/haven.jpg' },
		{ name: 'Icebox', image: '/icebox.jpg' },
		{ name: 'Bind', image: '/bind.jpg' },
		{ name: 'Ascent', image: '/ascent.jpg' }
	];

	const handleClick = (name) => {
		goto(`/mapas/${name}`);
	};
</script>

<div class="background">
	<h1 class="title">MAPAS</h1>

	<div class="maps-container">
		{#each maps as map}
			<div class="map-card" on:click={() => handleClick(map.name)}>
				<img class="map-image" src={map.image} alt={map.name} />
				<div class="map-name">{map.name}</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.background {
		background-image: url("/background-mapas.jpg");
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center;
		background-attachment: fixed;
		height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 20px;
	}

	.title {
		font-size: 500%;
		color: white;
		margin-bottom: 50px;
		text-align: center;
	}

	.maps-container {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 20px;
		padding: 20px;
	}

	.map-card {
		background-color: #1a2633;
		border-radius: 10px;
		overflow: hidden;
		text-align: center;
		width: 20%;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
		transition: transform 0.2s;
		cursor: pointer;
	}

	.map-card:hover {
		transform: scale(1.05);
	}

	.map-image {
		width: 100%;
		height: auto;
	}

	.map-name {
		padding: 10px;
		color: white;
		font-weight: bold;
	}
</style>
