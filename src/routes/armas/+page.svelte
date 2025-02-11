<script>
	import { goto } from '$app/navigation';

	let weapons = [
		{ name: 'Odin', image: '/odincard.jpg' },
		{ name: 'Vandal', image: '/vandalcard.jpg' },
		{ name: 'Outlaw', image: '/outlawcard.jpg' },
		{ name: 'Phantom', image: '/phantomcard.jpg' }
	];

	const handleClick = (name) => {
		goto(`/armas/${name}`);
	};
</script>

<div class="background">
	<h1 class="title">ARMAS</h1>

	<div class="weapons-container">
		{#each weapons as weapon}
			<div class="weapon-card" on:click={() => handleClick(weapon.name)}>
				<img class="weapon-image" src={weapon.image} alt={weapon.name} />
				<div class="weapon-name">{weapon.name}</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.background {
		background-image: url("/background-armas.jpg");
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

	.weapons-container {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 20px;
		padding: 20px;
	}

	.weapon-card {
		background-color: #1a2633;
		border-radius: 10px;
		overflow: hidden;
		text-align: center;
		width: 20%;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
		transition: transform 0.2s;
		cursor: pointer;
	}

	.weapon-card:hover {
		transform: scale(1.05);
	}

	.weapon-image {
		width: 100%;
		height: auto;
	}

	.weapon-name {
		padding: 10px;
		color: white;
		font-weight: bold;
	}
</style>
 