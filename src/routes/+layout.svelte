<script>
	import { writable } from 'svelte/store';
	import { goto } from '$app/navigation';
  import "../global.css";

	const personagens = [
		{ type: 'characters', name: 'Jett', id: 1, description: 'Descrição do Jett' },
		{ type: 'characters', name: 'Phoenix', id: 2, description: 'Descrição do Phoenix' },
		{ type: 'characters', name: 'Sage', id: 3, description: 'Descrição do Sage' },
		{ type: 'characters', name: 'Raze', id: 4, description: 'Descrição do Raze' }
	];

	const armas = [
		{ type: 'weapons', name: 'Vandal', id: 1, description: 'Descrição da Vandal' },
		{ type: 'weapons', name: 'Phantom', id: 2, description: 'Descrição da Phantom' },
		{ type: 'weapons', name: 'Sheriff', id: 3, description: 'Descrição do Sheriff' },
		{ type: 'weapons', name: 'Operator', id: 4, description: 'Descrição do Operator' }
	];

	const mapas = [
		{ type: 'maps', name: 'Bind', id: 1, description: 'Descrição do Bind' },
		{ type: 'maps', name: 'Haven', id: 2, description: 'Descrição do Haven' },
		{ type: 'maps', name: 'Ascent', id: 3, description: 'Descrição do Ascent' },
		{ type: 'maps', name: 'Icebox', id: 4, description: 'Descrição do Icebox' }
	];

	export const filteredResults = writable({
		characters: [],
		weapons: [],
		maps: []
	});

	let query = '';
	let selectedItem = null;

	function filterResults(query) {
		if (!query) {
			filteredResults.set({
				characters: [],
				weapons: [],
				maps: []
			});
			return;
		}

		const filteredCharacters = personagens.filter((character) =>
			character.name.toLowerCase().includes(query.toLowerCase())
		);

		const filteredWeapons = armas.filter((weapon) =>
			weapon.name.toLowerCase().includes(query.toLowerCase())
		);

		const filteredMaps = mapas.filter((map) =>
			map.name.toLowerCase().includes(query.toLowerCase())
		);

		filteredResults.set({
			characters: filteredCharacters,
			weapons: filteredWeapons,
			maps: filteredMaps
		});
	}

	$: filterResults(query);

	function selectItem(item) {
		const basePath = item.type === 'characters' ? 'personagens' : item.type === 'weapons' ? 'armas' : 'mapas';
    query = ''
		goto(`/${basePath}/${item.name.toLowerCase()}`);
	}
</script>

<nav class="navbar navbar-expand-lg bg-light navbar-light">
	<div class="container-fluid">
		<a class="navbar-brand" href="/">
			<img src="/logo.png" alt="Logo" width="100" height="100" />
		</a>
		<button
			class="navbar-toggler"
			type="button"
			data-bs-toggle="collapse"
			data-bs-target="#navbarSupportedContent"
			aria-controls="navbarSupportedContent"
			aria-expanded="false"
			aria-label="Toggle navigation"
		>
			<span class="navbar-toggler-icon"></span>
		</button>
		<div class="collapse navbar-collapse" id="navbarSupportedContent">
			<ul class="navbar-nav me-auto mb-2 mb-lg-0">
				<li class="nav-item">
					<a class="nav-link" href="/" style="font-size: 30px;">INÍCIO</a>
				</li>
				<li class="nav-item">
					<a class="nav-link" href="/sobre" style="font-size: 30px;">SOBRE</a>
				</li>
				<li class="nav-item">
					<a class="nav-link" href="/personagens" style="font-size: 30px;">AGENTES</a>
				</li>
				<li class="nav-item">
					<a class="nav-link" href="/armas" style="font-size: 30px;">ARMAS</a>
				</li>
        <li class="nav-item">
					<a class="nav-link" href="/mapas" style="font-size: 30px;">MAPAS</a>
				</li>
			</ul>
			<form class="d-flex" role="search">
				<input
					type="text"
					bind:value={query}
					placeholder="BUSCAR"
					class="form-control"
					style="font-size: 30px; width: 100%; margin-bottom: 20px;"
				/>
			</form>
		</div>
	</div>
</nav>

<!-- Resultados da busca -->
{#if query}
	<div class="search-results">
		<ul>
			{#each $filteredResults.characters as character}
				<li on:click={() => selectItem(character)}>
					{character.name}
				</li>
			{/each}
			{#each $filteredResults.weapons as weapon}
				<li on:click={() => selectItem(weapon)}>
					{weapon.name}
				</li>
			{/each}
			{#each $filteredResults.maps as map}
				<li on:click={() => selectItem(map)}>
					{map.name}
				</li>
			{/each}
		</ul>
	</div>
{/if}

<!-- Detalhes do item selecionado -->
{#if selectedItem}
	<div class="item-details">
		<h2>{selectedItem.name}</h2>
		<p>{selectedItem.description}</p>
	</div>
{/if}

<slot></slot>

<style>
	.navbar {
		padding: 10px 20px;
	}
	.search-results {
		position: absolute;
		background: rgb(0, 0, 0);
		border: 1px solid #7c7c7c;
		width: 100%;
		max-width: 600px;
		z-index: 1000;
	}
	.search-results ul {
		list-style: none;
		padding: 0;
		margin: 0;
	}
	.search-results li {
		padding: 10px;
		cursor: pointer;
	}
	.search-results li:hover {
		background: #6e6e6e;
	}
	.item-details {
		margin-top: 20px;
		padding: 20px;
		border: 1px solid #ccc;
		background: #f9f9f9;
	}
</style>
