<script>
	import { pokemon } from '../stores/pokestore.js';
	import PokeCard from '$lib/pokeCard.svelte';
	console.log($pokemon);

	let searchTerm = '';
	let filteredPokemon = [];

	$: {
		console.log(searchTerm);
		if (searchTerm.length > 0) {
			filteredPokemon = $pokemon.filter((poke) => {
				return poke.name.toLowerCase().includes(searchTerm.toLowerCase());
			});
		} else {
			filteredPokemon = $pokemon;
		}
	}
</script>

<svelte:head>
	<title>Svelte Kit Pokedex</title>
</svelte:head>

<h1 class="text-4xl text-center my-8 uppercase">Svelt Kit Pokedex</h1>

<input
	type="text"
	placeholder="Search Pokemon"
	class="w-full rounded-md text-lg p-4 boder-2 border-gray-200"
	bind:value={searchTerm}
/>
<div class="py-4 grid gap-4 md:grid-cols-2 grid-cols-1">
	{#each filteredPokemon as pokemon}
		<PokeCard {pokemon} />
	{/each}
</div>
